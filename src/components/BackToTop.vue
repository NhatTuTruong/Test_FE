<template>
    <button 
      @click="toggleScroll"
      class="fixed bottom-4 right-4 rounded-ful"
    >
    <img 
      :src="isTop ? '/images/icon/arrow-circle-up.png' : '/images/icon/arrow-circle-down.png'" 
      alt="Scroll Icon" 
      class="w-20 cursor-pointer"
    />
    </button>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue';
  
  const isTop = ref(true);
  
  const checkScroll = () => {
    const scrollY = window.scrollY;
    const scrollHeight = document.documentElement.scrollHeight;
    const clientHeight = window.innerHeight;
  
    isTop.value = scrollY < scrollHeight / 2; 
  };
  
  const toggleScroll = () => {
    if (isTop.value) {
      window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' }); 
    } else {
      window.scrollTo({ top: 0, behavior: 'smooth' }); 
    }
  };
  
  onMounted(() => {
    window.addEventListener('scroll', checkScroll);
  });
  
  onUnmounted(() => {
    window.removeEventListener('scroll', checkScroll);
  });
  </script>
  
  <style scoped>
  button {
    width: 50px;
    height: 50px;
    font-size: 20px;
  }
  </style>
  