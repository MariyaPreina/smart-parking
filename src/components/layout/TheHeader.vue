<template>
  <header class="header">
    <div class="container header-inner">
      <div class="logo">
        <a href="#hero" class="logo-link">
          <img src="@/assets/images/logo.svg" alt="Smart Parking Logo" />
        </a>
      </div>

      <nav class="navigation">
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About us</a></li>
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
  padding: 1rem 0;
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
    gap: 2.5rem;
    padding: 0;

    li a {
      text-decoration: none;
      color: #333;
      font-weight: 500;
      transition: color 0.3s;

      &:hover {
        color: #4f46e5;
      }
    }
  }
}
</style>
