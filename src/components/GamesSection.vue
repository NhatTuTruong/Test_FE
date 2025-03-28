
<template>
  <div class="our-games pt-10 pb-20">
    <h2 class="text-center text-5xl font-bold mb-6 text-black font-playfair">{{$t('ourGames')}}</h2>
    <p class="text-center mb-8  text-[#757575] p-2  max-w-[800px] mx-auto">{{$t('ourGamesDescription')}}</p>

    <div class="grid grid-cols-2 md:grid-cols-4 gap-6 px-10 max-w-[1440px] mx-auto pb-20">
      <div v-for="(game, index) in games" :key="index" 
           :class="{'relative top-20': index % 4 === 1 || index % 4 === 3}" 
           class="relative bg-white rounded-lg overflow-hidden">
        <div class="h-120 bg-cover bg-center rounded-xl cursor-pointer" :style="{ backgroundImage: `url(${game.image})`, backgroundSize: `cover` }">
          <div class="bg-opacity-50 w-full h-full flex flex-col justify-end p-8">
            <h2 class="text-[40px] font-bold text-white text-left">{{ game.title }}</h2>
            <p class="text-sm text-gray-300 text-left">{{ game.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const games = ref([
  { title: 'E-Space', image: '/images/BG1.png', description: 'An epic space adventure.' },
  { title: 'Kingland', image: '/images/BG2.png', description: 'Embark on a medieval journey.' },
  { title: 'The Last Game', image: '/images/BG3.png', description: 'Survive the final battle.' },
  { title: 'G-Dragon', image: '/images/BG4.png', description: 'Train your dragon and conquer.' },
  { title: 'Pirates', image: '/images/BG5.png', description: 'Sail the seas and find treasures.' },
  { title: 'Witch Party', image: '/images/BG6.png', description: 'Unleash your magical powers.' },
  { title: 'Rocky', image: '/images/BG7.png', description: 'Explore rocky terrains and secrets.' },
  { title: 'Blue Fire', image: '/images/BG8.png', description: 'Master the power of fire and ice.' },
  { title: 'Magic Tree', image: '/images/BG9.png', description: 'A mystical forest of wonders.' },
  { title: 'Aborigines', image: '/images/BG10.png', description: 'Uncover the ancient tribes.' },
  { title: 'Cinderella', image: '/images/BG11.png', description: 'A fairytale reimagined.' },
  { title: 'Egypt Game', image: '/images/BG12.png', description: 'Adventure in the deserts of Egypt.' }
]);
</script>

<style scoped>

</style>
