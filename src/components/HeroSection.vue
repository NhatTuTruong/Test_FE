<template>
  <HeaderComponent />
  <div class="hero-section relative h-[100vh] bg-cover bg-center flex flex-col items-center justify-center text-white">
    <div class="text-center z-10">
      <h1 class="text-5xl font-bold mb-10">We're Getting Ready</h1>
      <div class="gap-6 mb-6 flex justify-center pb-16">
        <div class="bg-white rounded-md flex justify-center w-[500px]">
          <div v-for="(value, label) in timeLeft" :key="label" class=" text-gray-900 p-4 rounded-md w-35">
            <span class="text-2xl font-bold">{{ value }}</span>
            <div class="text-sm uppercase">{{ label }}</div>
          </div>
        </div>
      </div>
      <div class="mb-4 flex justify-center">
        <p class="w-[70%] justify-center">We will be back to something amazing. 
          Please sign up to our newsletter for updates.</p>
      </div>
      <div class="flex items-center border rounded-md overflow-hidden w-100 mx-auto">
        <input type="email" placeholder="Enter your email" class="p-2 flex-1 outline-none bg-white placeholder-gray-300">
        <button class="text-black px-4 h-10 bg-white cursor-pointer">→</button>
      </div>
      <img class="z-2 absolute top-25 left-0 w-[550px] h-auto object-cover" src="/images/Fairy.png" alt="">
    </div>
    <svg class="absolute bottom-0 left-0 w-full z-1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 220">
      <path fill="#ffffff" fill-opacity="1" d="M0,0 C360,175 1080,175 1440,0 V220 H0 Z"></path>
    </svg>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import HeaderComponent from './Header.vue';

const timeLeft = ref({ days: 0, hours: 0, minutes: 0, seconds: 0 });

const countdown = () => {
  const targetDate = new Date('2025-12-31T23:59:59').getTime();

  const updateCountdown = () => {
    const now = new Date().getTime();
    const timeDifference = targetDate - now;

    if (timeDifference <= 0) {
      clearInterval(timer);
      return;
    }

    timeLeft.value = {
      days: Math.floor(timeDifference / (1000 * 60 * 60 * 24)),
      hours: Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
      minutes: Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60)),
      seconds: Math.floor((timeDifference % (1000 * 60)) / 1000),
    };
  };

  const timer = setInterval(updateCountdown, 1000);
  updateCountdown();

  onUnmounted(() => clearInterval(timer));
};

onMounted(countdown);
</script>

<style scoped>
.hero-section {
  background-image: url('/path-to-your-image.jpg');
  background-size: cover;
  background-position: center;
}
</style>