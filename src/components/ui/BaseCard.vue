<script setup>
import { defineProps } from 'vue';

defineProps({
  icon: {
    type: String,
  },
  title: {
    type: String,
    required: true
  },
  text: {
    type: String,
    required: true
  }
});
</script>

<template>
  <div class="base-card">
    <h4 class="title">
      <span class="icon">{{icon}}</span>
      {{ title}}
    </h4>
    <p class="text">{{text}}</p>
  </div>
</template>

<style scoped lang="scss">
.base-card {
  padding: 30px 20px 20px 50px;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  background-color: white;
}

.title {
  margin-bottom: 12px;
  position: relative;
  text-transform: uppercase;
  font-size: 20px;
  font-weight: 500;
  color: $color-black;
}

.icon {
  position: absolute;
  left: -30px;
  top: -3px;
  font-size: 25px;
}

.text {
  font-size: 16px;
  color: $color-grey-600;
}
</style>
