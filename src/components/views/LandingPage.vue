<script setup>
import HeroSection from '@/components/sections/HeroSection.vue'
import AboutSection from '@/components/sections/AboutSection.vue'
import AdvantagesSection from '@/components/sections/AdvantagesSection.vue'
import FeaturesSection from '@/components/sections/FeaturesSection.vue'
import InterfacesSection from '@/components/sections/InterfacesSection.vue'
import UsersSection from '@/components/sections/UsersSection.vue'
import WhyUsSection from '@/components/sections/WhyUsSection.vue'
import ContactFormSection from '@/components/sections/ContactFormSection.vue'
</script>

<template>
  <div class="landing-page">
    <main>
      <HeroSection />
      <AboutSection />
      <AdvantagesSection />
      <FeaturesSection />
      <UsersSection />
      <InterfacesSection />
      <WhyUsSection />
      <ContactFormSection />
    </main>
  </div>
</template>
