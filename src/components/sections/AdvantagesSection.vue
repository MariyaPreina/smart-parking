<template>
  <section id="advantages" class="advantages-section">
    <div class="container">
      <h2 class="title">Преимущества</h2>
      <div class="cards-container">
        <div class="card">
          <div class="icon">
            <img src="@/assets/images/search_p.svg" alt="car icon" />
          </div>
          <p class="text">Поиск свободных мест в реальном времени</p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="@/assets/images/camera.svg" alt="car icon" />
          </div>
          <p class="text"> Интеграция с видеокамерами</p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="@/assets/images/map.svg" alt="car icon" />
          </div>
          <p class="text">Удобная навигация до места</p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="@/assets/images/alarm.svg" alt="car icon" />
          </div>
          <p class="text">Экономия 10-15 минут на каждую поездку</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.advantages-section {
  padding: 100px 0;
  background-image: url('@/assets/images/background-mini.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
}

.title {
  font-size: 40px;
  font-weight: 600;
  text-transform: uppercase;
  text-align: center;
  margin-bottom: 40px;
  color: $color-white;
}

.cards-container {
  display: flex;
  gap: 20px;
  .card {
    flex: 1;
    padding: 20px;
    border-radius: 10px;
    background-color: $color-white;
    text-align: center;
  }
}

.icon {
  width: 90px;
  height: 90px;
  margin: 0 auto;
}

.text {
  margin-top: 10px;
}
</style>
