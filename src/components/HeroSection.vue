<template>
  <HeaderComponent />
  <div class="hero-section relative h-[100vh] bg-cover bg-center flex flex-col items-center justify-center text-white">
    <div class="text-center z-10">
      <h1 class="text-[60px] font-bold mb-10 font-playfair">{{ $t('comingSoon') }}</h1>
      <div class="gap-6 mb-6 flex justify-center pb-16">
        <div class="bg-white rounded-md flex justify-center max-w-[500px]">
          <div v-for="(value, label) in timeLeft" :key="label" class=" text-black p-4 rounded-md w-35">
            <span class="text-4xl font-bold font-playfair">{{ value }}</span>
            <div class="text-sm uppercase mt-5 font-bold">{{ label }}</div>
          </div>
        </div>
      </div>
      <div class="mb-4 flex justify-center">
        <p class="w-[70%] justify-center">{{ $t('des_banner') }}</p>
      </div>
      <div class="flex items-center border rounded-md overflow-hidden max-w-100 mx-auto">
        <input type="email" :placeholder="$t('text_input')" class="p-2 flex-1 outline-none text-black bg-white placeholder-gray-300">
        <button class="text-black px-4 h-10 bg-white cursor-pointer">➔</button>
      </div>
      <img class="z-2 absolute top-25 left-0 max-w-[550px] h-auto object-cover" src="/images/Fairy.png" alt="">
    </div>
    <svg class="absolute bottom-[-2px] left-0 w-full z-1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 220">
      <path fill="#ffffff" fill-opacity="1" d="M0,0 C360,175 1080,175 1440,0 V220 H0 Z"></path>
    </svg>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import HeaderComponent from './Header.vue';
import { useI18n } from 'vue-i18n';

const { t } = useI18n();


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
      [t('days')]: Math.floor(timeDifference / (1000 * 60 * 60 * 24)),
      [t('hours')]: Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
      [t('minutes')]: Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60)),
      [t('seconds')]: Math.floor((timeDifference % (1000 * 60)) / 1000),
    };
  };

  const timer = setInterval(updateCountdown, 1000);
  updateCountdown();

  onUnmounted(() => clearInterval(timer));
};

onMounted(countdown);

useHead({
  link: [
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700;800&display=swap"
    }
  ]
});
</script>

<style scoped>
.hero-section {
  color: #fff;
  background-image: url('/images/Rectangle 3462.png');
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
}

.hero-section {
  color: #fff;
  background-image: url('/images/Rectangle 3462.png');
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
}


/* Responsive Design */
@media (max-width: 768px) {

  .hero-section {
    height: 70vh;
  }

  .hero-section img {
    display: none;
  }

  .text-center h1 {
    font-size: 2rem; 
    margin-bottom: 1.5rem;
  }

  .gap-6 {
    gap: 1rem; 
  }

  .bg-white .rounded-md {
    max-width: 100%; 
    width: 100%;
  }

  .text-2xl {
    font-size: 1.5rem; 
  }

  .w-[70%] {
    width: 90%; 
  }

  .flex.items-center {
    width: 100%; 
  }

  input[type="email"] {
    width: 100%; 
    border-bottom-left-radius: 6px;
    border-bottom-right-radius: 6px;
  }

  .z-2 {
    max-width: 300px; /
    top: 15%; 

  .svg {
    bottom: -5px; 
  }
}
</style>