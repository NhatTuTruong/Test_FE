<template>
  <div class="landing-page font-sans text-white bg-gray-900 text-center">
    <HeroSection />
    <AboutSection />
    <GamesSection />
    <PartnersSection />
    <FooterSection />
  </div>
</template>

<script setup>
import HeroSection from './src/components/HeroSection.vue';
import AboutSection from './src/components/AboutSection.vue';
import GamesSection from './src/components/GamesSection.vue';
import PartnersSection from './src/components/PartnersSection.vue';
import FooterSection from './src/components/FooterSection.vue';
</script>

<style scoped>
.landing-page {
  font-family: Arial, sans-serif;
  color: #fff;
  background-image: url('/images/Rectangle 3462.png');
  position: relative;
  background-size: contain;
}
</style>