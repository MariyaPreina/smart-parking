<template>
  <section id="whyUs" class="why-us-section bg-large">
    <div class="container">
      <h2 class="section-title">Почему Smart Parking?</h2>
      <p class="section-subtitle">Сравнение с конкурентами</p>

      <div class="comparison-table-wrapper">
        <table class="comparison-table">
          <thead>
          <tr>
            <th>Функция</th>
            <th>Конкуренты</th>
            <th>Smart Parking</th>
          </tr>
          </thead>
          <tbody>
          <tr>
            <td>Графическое отображение зон</td>
            <td class="competitor">
              <span class="icon available">✓</span>
              <span class="status">Полное покрытие</span>
            </td>
            <td class="smart-parking">
              <span class="icon available">✓</span>
              <span class="status">Полное покрытие</span>
            </td>
          </tr>
          <tr>
            <td>Актуальная информация о свободных местах</td>
            <td class="competitor">
              <span class="icon unavailable">✕</span>
              <span class="status">Отсутствует</span>
            </td>
            <td class="smart-parking">
              <span class="icon available">✓</span>
              <span class="status">В реальном времени</span>
            </td>
          </tr>
          <tr>
            <td>ИИ-мониторинг в реальном времени</td>
            <td class="competitor">
              <span class="icon unavailable">✕</span>
              <span class="status">Отсутствует</span>
            </td>
            <td class="smart-parking">
              <span class="icon available">✓</span>
              <span class="status">Продвинутые алгоритмы</span>
            </td>
          </tr>
          <tr>
            <td>Распознавание знаков запрета</td>
            <td class="competitor">
              <span class="icon unavailable">✕</span>
              <span class="status">Отсутствует</span>
            </td>
            <td class="smart-parking">
              <span class="icon available">✓</span>
              <span class="status">Автоматическое</span>
            </td>
          </tr>
          </tbody>
        </table>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.why-us-section {
  padding: 100px 0;
  position: relative;
  color: $color-white;
}

.bg-large {
  position: relative;
  overflow: hidden;

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: url('@/assets/images/bg-large.png');
    background-size: cover;
    z-index: 1;
  }
}

.container {
  position: relative;
  z-index: 2;
}

.section-title {
  font-size: 40px;
  font-weight: 600;
  text-transform: uppercase;
  text-align: center;
  margin-bottom: 16px;
}

.section-subtitle {
  font-size: 18px;
  text-align: center;
  margin-bottom: 60px;
  color: rgba($color-white, 0.9);
}

.comparison-table-wrapper {
  max-width: 900px;
  margin: 0 auto;
  overflow-x: auto;
  border-radius: 12px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
}

.comparison-table {
  width: 100%;
  border-collapse: collapse;
  background-color: rgba($color-white, 0.05);
  backdrop-filter: blur(10px);

  th, td {
    padding: 20px;
    text-align: left;
    border-bottom: 1px solid rgba($color-white, 0.1);
  }

  th {
    font-weight: 600;
    font-size: 18px;
    text-transform: uppercase;
    background-color: rgba($color-white, 0.1);
  }

  td {
    font-size: 16px;

    &:first-child {
      font-weight: 500;
    }
  }

  tbody tr {
    transition: background-color 0.3s ease;

    &:hover {
      background-color: rgba($color-white, 0.08);
    }

    &:last-child td {
      border-bottom: none;
    }
  }
}

.icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 28px;
  height: 28px;
  border-radius: 50%;
  margin-right: 12px;
  font-size: 14px;

  &.available {
    background-color: rgba(#10b981, 0.2);
    color: #10b981;
  }

  &.limited, &.partial {
    background-color: rgba(#f59e0b, 0.2);
    color: #f59e0b;
  }

  &.unavailable {
    background-color: rgba(#ef4444, 0.2);
    color: #ef4444;
  }
}

.status {
  font-size: 15px;
}
</style>
<script setup lang="ts">
</script>
