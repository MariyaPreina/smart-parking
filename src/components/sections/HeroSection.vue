<script setup>
import TheHeader from '@/components/layout/TheHeader.vue'
import BaseButton from '@/components/ui/BaseButton.vue'

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({
      behavior: 'smooth',
      block: 'start',
    })
  }
}
</script>

<template>
  <section id="hero" class="hero-section">
    <TheHeader />
    <div class="hero-inner">
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="title">Smart Parking</h1>
            <p class="text">
              Smart Parking — интеллектуальная система видеоаналитики парковочных мест. Помогаем
              бизнесу управлять парковками с помощью компьютерного зрения и ИИ.
            </p>
            <BaseButton @click="scrollToSection('about')">Узнать больше</BaseButton>
          </div>

          <div class="hero-image">
            <img src="@/assets/images/hero-img.png" alt="Smart Parking Illustration" />
          </div>
        </div>
      </div>

      <div class="wave-background">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 1440 320"
          preserveAspectRatio="none"
          class="wave-svg"
        >
          <path
            fill="url(#wave-gradient)"
            d="M0,192L60,186.7C120,181,240,171,360,181.3C480,192,600,224,720,229.3C840,235,960,213,1080,202.7C1200,192,1320,192,1380,192L1440,192L1440,320L1380,320C1320,320,1200,320,1080,320C960,320,840,320,720,320C600,320,480,320,360,320C240,320,120,320,60,320L0,320Z"
          ></path>
          <defs>
            <linearGradient id="wave-gradient" x1="0%" y1="0%" x2="100%" y2="0%">
              <stop offset="0%" style="stop-color: #4f46e5; stop-opacity: 1" />
              <stop offset="100%" style="stop-color: #818cf8; stop-opacity: 1" />
            </linearGradient>
          </defs>
        </svg>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero-section {
  display: flex;
  position: relative;
  width: 100%;
  min-height: 100vh;
  overflow: hidden;
}

.hero-inner {
  display: flex;
  align-items: center;
  margin: auto;
}

.hero-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.hero-text {
  max-width: 500px;

  .title {
    color: $color-purple-1000;
    font-size: 45px;
    font-weight: 600;
    line-height: 1.1;
    margin: 0 0 20px;
    text-transform: uppercase;
  }

  .text {
    color: $color-grey-500;
    margin-bottom: 20px;
    font-size: 18px;
    line-height: 1.6;
  }
}

.hero-image {
  width: 70%;

  img {
    width: 100%;
    height: auto;
    object-fit: contain;
  }
}

.wave-background {
  position: absolute;
  top: 0;
  right: 0;
  width: 70%;
  height: 100%;
  background: linear-gradient(135deg, $color-purple-600 0%, $color-purple-400 100%);
  clip-path: polygon(100% 0, 100% 100%, 0 100%, 70% 0);
  z-index: 1;
}

.wave-svg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: rotate(180deg) scaleX(1.5);
  transform-origin: center;
}
</style>
