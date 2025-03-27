<template>
  <div class="landing-page font-sans text-white text-center">
    <HeroSection />
    <AboutSection />
    <GamesSection />
    <PartnersSection />
    <FooterSection />
    <BackToTop />
  </div>
</template>

<script setup>
import HeroSection from './src/components/HeroSection.vue';
import AboutSection from './src/components/AboutSection.vue';
import GamesSection from './src/components/GamesSection.vue';
import PartnersSection from './src/components/PartnersSection.vue';
import FooterSection from './src/components/FooterSection.vue';
import BackToTop from './src/components/BackToTop.vue';
</script>

<style>
.landing-page {
  font-family: Montserrat, sans-serif;
}

@font-face {
    font-family: 'Playfair Display';
    src: url('/assets/fonts/PlayfairDisplay-Regular.woff2') format('woff2'),
         url('/assets/fonts/PlayfairDisplay-Regular.woff') format('woff');
    font-weight: 400;
    font-style: normal;
}

.font-playfair {
    font-family: 'Playfair Display', serif;
}


</style>