<script setup>
const currentYear = new Date().getFullYear();

const mainLinks = [
  { name: 'О приложении', href: '#about' },
  { name: 'Преимущества', href: '#advantages' },
  { name: 'Возможности', href: '#features' },
  { name: 'Пользователи', href: '#users' }
];

const additionalLinks = [
  { name: 'Интерфейс', href: '#interface' },
  { name: 'Почему мы', href: '#whyUs' },
  { name: 'Написать нам', href: '#contactUs' }
];

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId.replace('#', ''));
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <img src="@/assets/images/logo.svg" alt="Smart Parking Logo" class="logo" />
          <p class="tagline">Интеллектуальная система мониторинга парковочных мест</p>
        </div>

        <div class="footer-links">
          <div class="links-column">
            <h4 class="column-title">Навигация</h4>
            <ul>
              <li v-for="(link, index) in mainLinks" :key="index">
                <a :href="link.href" @click.prevent="scrollToSection(link.href)">{{ link.name }}</a>
              </li>
            </ul>
          </div>

          <div class="links-column">
            <h4 class="column-title">Дополнительно</h4>
            <ul>
              <li v-for="(link, index) in additionalLinks" :key="index">
                <a :href="link.href" @click.prevent="scrollToSection(link.href)">{{ link.name }}</a>
              </li>
            </ul>
          </div>

          <div class="links-column">
            <h4 class="column-title">Контакты</h4>
            <ul class="contact-info">
              <li>
                <span class="icon">📱</span>
                <span>+7 (999) 123-45-67</span>
              </li>
              <li>
                <span class="icon">✉️</span>
                <span>info@smartparking.ru</span>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <p class="copyright">© {{ currentYear }} Smart Parking. Все права защищены.</p>
      </div>
    </div>
  </footer>
</template>

<style scoped lang="scss">
.footer {
  background-color: $color-purple-1000;
  color: white;
  padding: 60px 0 30px;
}

.footer-content {
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
  margin-bottom: 40px;
}

.footer-logo {
  flex: 1;
  min-width: 250px;

  .logo {
    height: 40px;
    margin-bottom: 15px;
  }

  .tagline {
    font-size: 14px;
    color: rgba(white, 0.7);
    line-height: 1.5;
  }
}

.footer-links {
  flex: 2;
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
}

.links-column {
  flex: 1;
  min-width: 160px;

  .column-title {
    font-size: 16px;
    font-weight: 600;
    margin-bottom: 20px;
    color: white;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0;

    li {
      margin-bottom: 12px;

      a {
        color: rgba(white, 0.7);
        text-decoration: none;
        transition: color 0.3s ease;
        font-size: 14px;

        &:hover {
          color: white;
        }
      }
    }
  }
}

.contact-info {
  li {
    display: flex;
    align-items: center;
    margin-bottom: 15px;

    .icon {
      margin-right: 10px;
      font-size: 16px;
    }

    span {
      color: rgba(white, 0.7);
      font-size: 14px;
    }
  }
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 30px;
  border-top: 1px solid rgba(white, 0.1);

  .copyright {
    color: rgba(white, 0.5);
    font-size: 14px;
  }
}
</style>
