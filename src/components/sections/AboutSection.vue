<script setup>
import BaseCard from '@/components/ui/BaseCard.vue'

const cards = [
  {
    icon: '🎯',
    title: 'Умное распознавание',
    text:
      'Наши алгоритмы искусственного интеллекта анализируют данные с городских видеокамер, ' +
      'точно определяя свободные и занятые парковочные места. Система учитывает габариты вашего автомобиля для подбора подходящих мест.',
  },
  {
    icon: '📱',
    title: 'Простота использования',
    text:
      'Интуитивно понятный интерфейс с картой в реальном времени, цветовой индикацией загруженности парковок и умной навигацией. ' +
      'Всего несколько кликов — и вы знаете, где припарковаться.',
  },
  {
    icon: '⚡️',
    title: 'Максимальная эффективность',
    text:
      'Приложение не только показывает свободные места, но и прогнозирует их освобождение, ' +
      'предупреждает о зонах запрета парковки и помогает спланировать оптимальный маршрут с учетом дорожной ситуации.',
  },
]
</script>

<template>
  <section id="about" class="about-section">
    <div class="inner container">
      <h2 class="title">О приложении</h2>
      <p class="text">
        Smart Parking — это инновационное решение, которое использует городские видеокамеры и
        искусственный интеллект для мониторинга парковочных мест в режиме реального времени.
        Приложение помогает водителям экономить время, снижать стресс и делает городскую среду более
        комфортной для всех участников движения.
      </p>
      <div class="content">
        <div class="image-container">
          <img
            src="@/assets/images/app-mockup-2.png"
            alt="Smart Parking System"
            class="about-image"
          />
        </div>
        <div class="cards-container">
          <BaseCard
            v-for="(card, i) in cards"
            :key="i"
            :icon="card.icon"
            :text="card.text"
            :title="card.title"
            class="card"
          ></BaseCard>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.about-section {
  padding: 120px;
  background-color: $color-white;
}

.title {
  font-size: 40px;
  font-weight: 600;
  text-transform: uppercase;
  text-align: center;
}

.text {
  margin: 20px auto;
  max-width: 70%;
  font-size: 16px;
  text-align: center;
  color: $color-grey-600;
}

.content {
  display: flex;
  align-items: stretch;
  margin-top: 60px;
}

.image-container {
  flex: 1;
  display: flex;
  align-items: center;

  .about-image {
    max-height: 600px;
    width: 100%;
    height: auto;
    object-fit: contain;
  }
}

.cards-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 30px;
}
</style>
