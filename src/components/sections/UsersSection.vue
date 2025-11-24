<template>
  <section id="users" class="users-section">
    <div class="container">
      <h2 class="title">Для кого это приложение</h2>
      <p class="section-description">
        Интеллектуальная система мониторинга парковочных мест с удобным интерфейсом и множеством полезных функций.
      </p>

      <div class="users-grid">
        <div class="users-item left-users">
          <div class="users-icon">
            <img src="@/assets/images/transport.svg" alt="Car Icon" />
          </div>
          <h3 class="users-title">Автовладельцы</h3>
          <p class="users-description">Приложение
            станет незаменимым помощником,
            позволит им сэкономить время и
            избежать стресса.</p>
        </div>
        <div class="app-mockup">
          <img src="@/assets/images/app/mockup1.png" alt="App Interface" />
        </div>

        <div class="users-item">
          <div class="users-icon">
            <img src="@/assets/images/camper.svg" alt="Camper Icon" />
          </div>
          <h3 class="users-title">Туристы и гости города</h3>
          <p class="users-description">Приложение поможет им быстро
            сориентироватся и найти
            подходящую парковку, сделав
            пребывание в городе более
            комфортным.</p>
        </div>


        <div class="users-item left-users">
          <div class="users-icon">
            <img src="@/assets/images/taxi.svg" alt="Taxi Icon" />
          </div>
          <h3 class="users-title">Водители такси и каршеринга</h3>
          <p class="users-description">Для водителей, занятых в сфере
            транспортных услуг, и пользователей
            каршеринга особо важно иметь
            возможность быстро находить
            парковочное место</p>
        </div>

        <div class="users-item">
          <div class="users-icon">
            <img src="@/assets/images/wheelchair.svg" alt="Wheelchair Icon" />
          </div>
          <h3 class="users-title">Люди с ограниченными возможностями</h3>
          <p class="users-description">
            Приложение может быть адаптировано
            для поиска парковочных мест,
            специально предназначенных для людей
            с ограниченными возможностями, делая
            городскую среду более доступной и
            комфортной для всех</p>
        </div>

        <div class="users-item left-users">
          <div class="users-icon">
            <img src="@/assets/images/courier.svg" alt="Courier Icon" />
          </div>
          <h3 class="users-title">Курьерские службы</h3>
          <p class="users-description">Приложение поможет им эффективнее планировать маршрут и обслуживать больше клиентов.</p>
        </div>


        <div class="users-item">
          <div class="users-icon">
            <img src="@/assets/images/business.svg" alt="Office Icon" />
          </div>
          <h3 class="users-title">Сотрудники офисов</h3>
          <p class="users-description">Ежедневный поиск парковки рядом с работой, особенно в деловых центрах</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.users-section {
  padding: 100px 0;
  background-image: url('@/assets/images/bg-large.png');
  background-size: cover;
  background-position: center;
  color: white;
  position: relative;
  overflow: hidden;
}

.title {
  font-size: 40px;
  font-weight: 600;
  text-transform: uppercase;
  text-align: center;
  margin-bottom: 40px;
  color: $color-white;
}

.section-description {
  max-width: 700px;
  margin: 0 auto 60px;
  text-align: center;
  font-size: 18px;
  line-height: 1.6;
}

.users-grid {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  gap: 30px 80px;
  align-items: center;
}

.users-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  margin-bottom: 60px;
  max-width: 300px;
}

.left-users {
  justify-self: end;
}

.users-icon {
  width: 70px;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;

  img {
    width: 100%;
    height: auto;
  }
}

.users-title {
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 15px;
  text-transform: uppercase;
}

.users-description {
  font-size: 16px;
  line-height: 1.5;
}

.app-mockup {
  grid-row: span 3;
  display: flex;
  justify-content: center;
  align-items: center;

  img {
    max-width: 100%;
    height: auto;
    max-height: 600px;
    filter: drop-shadow(0 10px 20px rgba(0, 0, 0, 0.3));
  }
}
</style>
