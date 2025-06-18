<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId);
  if (element) {
    element.scrollIntoView({
      behavior: 'smooth',
      block: 'start'
    });
  }
};

const isSticky = ref(false);
const scrollThreshold = 100;

const handleScroll = () => {
  isSticky.value = window.scrollY > scrollThreshold;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <header class="header" :class="{ 'sticky-header': isSticky }">
    <div class="container header-inner">
      <div class="logo">
        <a href="#hero" class="logo-link" @click.prevent="scrollToSection('hero')">
          <img src="@/assets/images/logo.svg" alt="Smart Parking Logo" />
        </a>
      </div>

      <nav class="navigation">
        <ul>
          <li><a href="#about" @click.prevent="scrollToSection('about')">О приложении</a></li>
          <li><a href="#about" @click.prevent="scrollToSection('advantages')">Преимущества</a></li>
          <li><a href="#course">Course</a></li>
          <li><a href="#pricing">Pricing</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>

      <button class="get-started-btn">Get Started</button>
    </div>
  </header>
</template>

<style scoped lang="scss">
.header {
  padding: 10px 0;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: transparent;
  z-index: 100;
  transition: all 0.3s ease;
}

.sticky-header {
  background-color: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(5px);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  padding: 0.5rem 0;
}

.header-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  width: 150px;
}

.navigation {
  ul {
    display: flex;
    list-style: none;
    gap: 25px;
    padding: 0;

    li a {
      text-decoration: none;
      color: $color-grey-1000;
      font-weight: 500;
      transition: color 0.3s;

      &:hover {
        color: $color-purple-600;
      }
    }
  }
}
</style>
