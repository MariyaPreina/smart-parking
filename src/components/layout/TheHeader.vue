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
const isDropdownOpen = ref(false);

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value;
};

const closeDropdown = () => {
  isDropdownOpen.value = false;
};

const handleScroll = () => {
  isSticky.value = window.scrollY > scrollThreshold;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
  document.addEventListener('click', (event) => {
    const dropdown = document.querySelector('.dropdown');
    if (dropdown && !dropdown.contains(event.target)) {
      closeDropdown();
    }
  });
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
  document.removeEventListener('click', closeDropdown);
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
          <li><div @click="scrollToSection('about')">О приложении</div></li>
          <li><div @click="scrollToSection('advantages')">Преимущества</div></li>
          <li><div @click="scrollToSection('features')">Возможности</div></li>
          <li><div href="#pricing">Pricing</div></li>
          <li class="dropdown" @click.stop>
            <div class="dropdown-toggle" @click="toggleDropdown">
              Дополнительно
              <span class="dropdown-arrow" :class="{ 'open': isDropdownOpen }">▼</span>
            </div>
            <ul class="dropdown-menu" v-show="isDropdownOpen">
              <li><div @click="scrollToSection('faq')">FAQ</div></li>
              <li><div @click="scrollToSection('blog')">Блог</div></li>
              <li><div @click="scrollToSection('support')">Поддержка</div></li>
            </ul>
          </li>
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

    li div {
      text-decoration: none;
      color: $color-grey-1000;
      font-weight: 500;
      transition: color 0.3s;
      cursor: pointer;

      &:hover {
        color: $color-purple-600;
      }
    }
  }
}

.dropdown {
  position: relative;

  .dropdown-toggle {
    display: flex;
    align-items: center;
    gap: 5px;
    cursor: pointer;
  }

  .dropdown-arrow {
    font-size: 10px;
    transition: transform 0.3s ease;

    &.open {
      transform: rotate(180deg);
    }
  }

  .dropdown-menu {
    position: absolute;
    top: 100%;
    left: 0;
    min-width: 180px;
    background-color: white;
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    padding: 10px 0;
    margin-top: 10px;
    display: flex;
    flex-direction: column;
    gap: 0;
    z-index: 101;

    li {
      width: 100%;

      div {
        display: block;
        padding: 8px 20px;
        width: 100%;

        &:hover {
          background-color: rgba($color-purple-600, 0.05);
        }
      }
    }
  }
}

</style>
