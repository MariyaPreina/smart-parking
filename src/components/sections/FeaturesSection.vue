<script setup>
import { ref } from 'vue'

const features = [
  {
    id: 1,
    title: 'Видеоаналитика',
    content: [
      'Распознавание занятости мест по видеопотоку.',
      'ИИ-анализ в режиме реального времени на базе Hailo-8 NPU.',
    ],
    icon: '🔍',
  },
  {
    id: 3,
    title: 'Управление парковкой',
    content: [
      'Веб-дашборд с картой загруженности.',
      'Статистика по часам, дням, зонам.',
      'История событий и отчёты для управляющих',
    ],
    icon: '🧭',
  },
  {
    id: 4,
    title: 'Дополнительные модули',
    content: [
      'Распознавание автомобильных номеров',
      'Контроль въезда и выезда',
      'Контроль платной парковки',
    ],
    icon: '🔔',
  },
  {
    id: 5,
    title: 'Модели подключения',
    content: [
      'CaaS — оборудование и ПО в аренду',
      'SaaS — подписка на платформу при наличии своего железа',
      'SDK — лицензирование для интеграторов и партнёров',
    ],
    icon: '👤',
  },
]

const activeFeature = ref(1)

const toggleFeature = (id) => {
  activeFeature.value = activeFeature.value === id ? null : id
}
</script>

<template>
  <section id="features" class="features-section">
    <div class="container">
      <h2 class="title">Возможности</h2>

      <div class="features-content">
        <div class="accordion">
          <div
            v-for="feature in features"
            :key="feature.id"
            class="accordion-item"
            :class="{ active: activeFeature === feature.id }"
          >
            <div class="accordion-header" @click="toggleFeature(feature.id)">
              <div class="icon">{{ feature.icon }}</div>
              <h3 class="accordion-title">{{ feature.title }}</h3>
              <div class="accordion-icon">
                <svg
                  width="16"
                  height="16"
                  viewBox="0 0 16 16"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                  :class="{ rotated: activeFeature === feature.id }"
                >
                  <path
                    d="M4 6L8 10L12 6"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
            </div>
            <div class="accordion-content" :class="{ expanded: activeFeature === feature.id }">
              <ul class="feature-list">
                <li v-for="(content, i) in feature.content" :key="i">
                  <span class="bullet"></span>
                  {{ content }}
                </li>
              </ul>
            </div>
          </div>
        </div>

        <div class="features-image">
          <img src="@/assets/images/feature-img.jpg" alt="Smart Parking Features" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.features-section {
  padding: 100px 0;
  background-color: $color-white;
}

.title {
  font-size: 40px;
  font-weight: 600;
  text-transform: uppercase;
  text-align: center;
}

.features-content {
  display: flex;
  align-items: center;
  gap: 60px;
}

.accordion {
  flex: 1;
  max-width: 600px;
}

.accordion-item {
  border: 1px solid rgba($color-grey-500, 0.2);
  border-radius: 10px;
  margin-bottom: 16px;
  overflow: hidden;
  transition: all 0.3s ease;

  &.active {
    border-color: $color-purple-600;
    box-shadow: 0 4px 20px rgba($color-purple-600, 0.1);
  }
}

.accordion-header {
  display: flex;
  align-items: center;
  padding: 20px;
  cursor: pointer;
  background-color: white;
  transition: background-color 0.3s ease;

  &:hover {
    background-color: rgba($color-purple-600, 0.03);
  }

  .icon {
    font-size: 24px;
    margin-right: 16px;
  }
}

.accordion-title {
  flex: 1;
  margin: 0;
  font-size: 18px;
  font-weight: 500;
  color: $color-grey-1000;
}

.accordion-icon {
  svg {
    transition: transform 0.3s ease;

    &.rotated {
      transform: rotate(180deg);
    }
  }
}

.accordion-content {
  max-height: 0;
  overflow: hidden;
  opacity: 0;
  transform: translateY(-10px);
  transition:
    max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1),
    padding 0.4s cubic-bezier(0.4, 0, 0.2, 1),
    opacity 0.3s ease,
    transform 0.3s ease;
  background-color: rgba($color-purple-600, 0.02);

  p {
    margin: 0;
    color: $color-grey-600;
    line-height: 1.6;
  }

  &.expanded {
    max-height: 200px;
    padding: 0 20px 20px;
    opacity: 1;
    transform: translateY(0);
  }
}

.feature-list {
  list-style: none;
  padding: 0;
  margin: 0;

  li {
    position: relative;
    padding-left: 24px;
    margin-bottom: 10px;
    color: $color-grey-600;
    line-height: 1.5;
    font-size: 15px;

    &:last-child {
      margin-bottom: 0;
    }

    .bullet {
      position: absolute;
      left: 0;
      top: 8px;
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: linear-gradient(135deg, $color-purple-600 0%, $color-purple-400 100%);
      display: block;
    }
  }
}

.features-image {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;

  img {
    max-width: 100%;
    height: auto;
  }
}
</style>
