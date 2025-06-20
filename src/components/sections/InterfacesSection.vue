<script>
import { Swiper, SwiperSlide } from 'swiper/vue'

import 'swiper/css'

import 'swiper/css/effect-coverflow'
import 'swiper/css/pagination'

import mockup1 from '@/assets/images/app/mockup1.png'
import mockup2 from '@/assets/images/app/mockup2.png'
import mockup3 from '@/assets/images/app/mockup3.png'
import mockup4 from '@/assets/images/app/mockup4.png'
import mockup5 from '@/assets/images/app/mockup5.png'
import mockup6 from '@/assets/images/app/mockup6.png'

import { EffectCoverflow, Pagination } from 'swiper/modules'

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const slides = [
      mockup1,
      mockup2,
      mockup3,
      mockup4,
      mockup5,
      mockup6
    ]
    return {
      modules: [EffectCoverflow, Pagination],
      slides
    }
  },
}
</script>

<template>
  <section id="interface" class="interfaces-section">
    <div class="container">
      <h2 class="title">Пользовательский интерфейс</h2>
      <p class="text">Smart Parking App: интуитивно понятный дизайн для городской мобильности.
        Приложение разработано с учетом потребностей современного водителя - быстро, удобно, информативно.</p>
      <div class="slider-container">
        <swiper
          :effect="'coverflow'"
          :grabCursor="true"
          :centeredSlides="true"
          :slidesPerView="5"
          :coverflowEffect="{
            rotate: 50,
            stretch: 0,
            depth: 100,
            modifier: 1,
            slideShadows: true,
          }"
          :pagination="true"
          :modules="modules"
          class="swiper"
        >
          <swiper-slide v-for="(slide, i) in slides" :key="i">
            <img :src="slide" alt="app interface image"/>
          </swiper-slide>
        </swiper>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.swiper-slide-shadow-coverflow {
  border-radius: 22px;
}

.swiper-pagination-bullet {
  width: 10px;
  height: 10px;
  background: $color-purple-400;
  opacity: 0.5;
}

.swiper-pagination-bullet-active {
  opacity: 1;
  background: $color-purple-600;
}
</style>

<style scoped lang="scss">
.interfaces-section {
  padding: 100px 0;
}

.title {
  font-size: 40px;
  font-weight: 600;
  text-transform: uppercase;
  text-align: center;
}

.text {
  margin: 20px auto 60px;
  max-width: 70%;
  font-size: 16px;
  text-align: center;
  color: $color-grey-600;
}

.slider-container {
  margin: 0 auto;
  max-width: 80%;
}

.swiper {
  width: 100%;
  height: 100%;
}
</style>
