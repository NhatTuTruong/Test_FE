<template>
    <header class="flex justify-between items-center p-4 bg-transparent text-white w-full">
        <div class="logo ml-4">
            <img src="../../public/images/White_logo.png" alt="Logo" class="h-12">
        </div>
        <nav class="flex gap-15 mr-4 text-[14px]">
            <a href="#about-us" class="hover:underline">About Us</a>
            <a href="#games" class="hover:underline">Games</a>
            <a href="#partners" class="hover:underline">Partners</a>
            <a href="#contact" class="hover:underline">Contact Us</a>


            <div class="relative">
                <div @click="toggleDropdown" class="cursor-pointer flex items-center gap-2 px-2 py-1">
                    <img :src="currentLang === 'en' ? '/images/united-states.png' : '/images/vietnam.png'" alt="Flag"
                        class="w-8 h-6" />
                </div>
                <div v-if="showDropdown"
                    class="absolute top-full right-0 w-35 bg-white text-black border rounded-md shadow-md mt-1">
                    <div @click="changeLanguage('en')"
                        class="flex items-center gap-2 px-4 py-2 cursor-pointer hover:bg-gray-100 hover:rounded-md">
                        <img src="/images/united-states.png" alt="English Flag" class="w-6 h-4" />
                        English
                    </div>

                    <div @click="changeLanguage('vi')"
                        class="flex items-center gap-2 px-4 py-2 cursor-pointer hover:bg-gray-100 hover:rounded-md">
                        <img src="/images/vietnam.png" alt="Vietnamese Flag" class="w-6 h-4" />
                        Tiếng Việt
                    </div>
                </div>
            </div>
        </nav>
    </header>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const currentLang = ref('en');
const showDropdown = ref(false);


const toggleDropdown = () => {
  showDropdown.value = !showDropdown.value;
};


const changeLanguage = (lang) => {
    alert('1');
    
  if (lang !== currentLang.value) {
    currentLang.value = lang;
    localStorage.setItem('preferredLanguage', lang);
  }
  showDropdown.value = false;
};


onMounted(() => {
  const savedLanguage = localStorage.getItem('preferredLanguage');
  if (savedLanguage) {
    currentLang.value = savedLanguage;
  }
});
</script>