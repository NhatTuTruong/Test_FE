<template>
  <div class="bg-[#F6F6F6]">
    <div class="our-partners py-20 max-w-[1200px] mx-auto">
      <h2 class="text-center text-4xl font-bold mb-6 text-black font-playfair">{{$t('partners')}}</h2>

      <div class="relative">
        <img src="/images/icon/arrow-square-left.png" alt="Previous"
          class="swiper-custom-prev absolute left-0 top-1/2 transform -translate-y-1/2 w-10 cursor-pointer z-10" />

        <Swiper ref="swiper" :slides-per-view="2" :breakpoints="{
          640: { slidesPerView: 3 },
          768: { slidesPerView: 4 },
          1024: { slidesPerView: 5 }
        }" :loop="true" :autoplay="{
          delay: 2000,
          disableOnInteraction: false
        }" class="partner-slider">
          <SwiperSlide v-for="(partner, index) in partners" :key="index">
            <img :src="partner.logo" :alt="partner.name" class="h-15 mx-auto" />
          </SwiperSlide>
        </Swiper>

        <img src="/images/icon/arrow-square-right.png" alt="Next"
          class="swiper-custom-next absolute right-0 top-1/2 transform -translate-y-1/2 w-10 cursor-pointer z-10" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';

const swiper = ref(null);

const partners = [
  { name: 'Partner 1', logo: '/images/Rectangle 58.png' },
  { name: 'Partner 2', logo: '/images/Rectangle 59.png' },
  { name: 'Partner 3', logo: '/images/Rectangle 60.png' },
  { name: 'Partner 4', logo: '/images/Rectangle 61.png' },
  { name: 'Partner 5', logo: '/images/Rectangle 62.png' },
  { name: 'Partner 6', logo: '/images/Rectangle 63.png' }
];

onMounted(() => {
  const swiperInstance = swiper.value.$el.swiper;

  document.querySelector('.swiper-custom-prev').addEventListener('click', () => {
    swiperInstance.slidePrev();
  });

  document.querySelector('.swiper-custom-next').addEventListener('click', () => {
    swiperInstance.slideNext();
  });
});
</script>

<style scoped>
.partner-slider img {
  object-fit: contain;
  width: 100%;
}


.swiper-custom-prev,
.swiper-custom-next {
  width: 40px;
  opacity: 0.8;
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.swiper-custom-prev:hover,
.swiper-custom-next:hover {
  opacity: 1;
  transform: scale(1.2);
}
</style>
