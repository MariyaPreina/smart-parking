<script setup>
import { ref } from 'vue'
import BaseButton from '@/components/ui/BaseButton.vue'

const formData = ref({
  name: '',
  email: '',
  message: '',
})

const isSubmitted = ref(false)
const isLoading = ref(false)
const errorMessage = ref('')

const submitForm = async () => {
  // Validate form
  if (!formData.value.name || !formData.value.email || !formData.value.message) {
    errorMessage.value = 'Пожалуйста, заполните все поля'
    return
  }

  // Email validation
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
  if (!emailRegex.test(formData.value.email)) {
    errorMessage.value = 'Пожалуйста, введите корректный email'
    return
  }

  errorMessage.value = ''
  isLoading.value = true

  // Simulate network request
  setTimeout(() => {
    isSubmitted.value = true
    isLoading.value = false
    formData.value = { name: '', email: '', message: '' }
  }, 1000)
}

const resetForm = () => {
  isSubmitted.value = false
}
</script>

<template>
  <div id="contactUs" class="feedback-form">
    <div class="container">
      <div class="content">
        <div class="form-inner"><h3 class="form-title">Обратная связь</h3>
          <p class="form-description">
            Остались вопросы или предложения? Напишите нам, и мы свяжемся с вами в ближайшее время.
          </p>

          <div v-if="isSubmitted" class="success-message">
            <div class="success-icon">✓</div>
            <h4>Спасибо за ваше сообщение!</h4>
            <p>Мы получили вашу заявку и свяжемся с вами в ближайшее время.</p>
            <BaseButton @click="resetForm">Отправить еще</BaseButton>
          </div>

          <form v-else @submit.prevent="submitForm" class="form-container">
            <div class="inputs-wrapper">
              <div class="form-group">
                <label for="name">Имя</label>
                <input
                  type="text"
                  id="name"
                  v-model="formData.name"
                  placeholder="Введите ваше имя"
                  :disabled="isLoading"
                />
              </div>

              <div class="form-group">
                <label for="email">Email</label>
                <input
                  type="email"
                  id="email"
                  v-model="formData.email"
                  placeholder="Введите ваш email"
                  :disabled="isLoading"
                />
              </div>
            </div>

            <div class="form-group">
              <label for="message">Сообщение</label>
              <textarea
                id="message"
                v-model="formData.message"
                placeholder="Введите ваше сообщение"
                rows="4"
                :disabled="isLoading"
              ></textarea>
            </div>

            <div v-if="errorMessage" class="error-message">
              {{ errorMessage }}
            </div>

            <div class="form-actions">
              <BaseButton type="submit" :disabled="isLoading">
                {{ isLoading ? 'Отправка...' : 'Отправить' }}
              </BaseButton>
            </div>
          </form>
        </div>

        <div class="image-container">
          <img src="@/assets/images/contactUs.jpg" alt="Feedback form image"/>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.feedback-form {
  padding: 30px;
  border-radius: 10px;
  background-color: white;
}

.content {
  width: 100%;
  display: flex;
}

.form-inner {
  max-width: 600px;
  margin: auto;
}

.image-container {
  flex: 1;
}

.form-title {
  font-size: 24px;
  font-weight: 600;
  color: $color-purple-1000;
  margin-bottom: 12px;
  text-transform: uppercase;
}

.form-description {
  color: $color-grey-600;
  margin-bottom: 24px;
  font-size: 16px;
  line-height: 1.5;
}

.form-container {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.inputs-wrapper {
  width: 100%;
  display: flex;
  gap: 20px;
  & .form-group {
    flex: 1;
  }
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 6px;

  label {
    font-weight: 500;
    color: $color-grey-600;
    font-size: 14px;
  }

  input,
  textarea {
    padding: 10px 14px;
    border: 1px solid rgba($color-grey-500, 0.3);
    border-radius: 8px;
    font-family: inherit;
    font-size: 15px;
    transition:
      border-color 0.3s ease,
      box-shadow 0.3s ease;

    &:focus {
      outline: none;
      border-color: $color-purple-600;
      box-shadow: 0 0 0 3px rgba($color-purple-600, 0.1);
    }

    &::placeholder {
      color: $color-grey-600;
    }

    &:disabled {
      background-color: rgba($color-grey-500, 0.05);
      cursor: not-allowed;
    }
  }

  textarea {
    resize: vertical;
    min-height: 100px;
  }
}

.form-actions {
  margin-top: 8px;
}

.error-message {
  color: $color-error;
  font-size: 14px;
  padding: 8px 12px;
  background-color: rgba($color-error, 0.08);
  border-radius: 6px;
}

.success-message {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 20px;

  .success-icon {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: linear-gradient(135deg, $color-purple-600 0%, $color-purple-400 100%);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 30px;
    margin-bottom: 16px;
  }

  h4 {
    font-size: 20px;
    font-weight: 600;
    color: $color-purple-1000;
    margin-bottom: 10px;
  }

  p {
    color: $color-grey-600;
    margin-bottom: 20px;
  }
}
</style>
