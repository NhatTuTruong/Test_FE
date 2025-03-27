<template>
    <header class="flex justify-between items-center p-4 bg-transparent text-white w-full absolute z-100">
        <div class="logo ml-4">
            <img src="../../public/images/White_logo.png" alt="Logo" class="h-12">
        </div>

        <div class="hamburger-menu md:hidden cursor-pointer" @click="toggleMobileMenu">
            <img src="/images/icon/menu.png" alt="Menu" class="w-8 h-8">
        </div>

        <nav :class="['nav-menu, z-40', { 'hidden': !showMobileMenu }]" 
             class="flex gap-5 mr-4 text-[14px] uppercase font-[700] md:flex md:relative md:bg-transparent md:text-white absolute top-0 left-0 w-full bg-white text-black bg-opacity-90 flex-col items-center z-50 md:flex-row md:items-center md:w-auto justify-center">
            <a href="#about-us" class="hover:underline px-4 py-2 text-center">{{ $t('aboutUs') }}</a>
            <a href="#games" class="hover:underline px-4 py-2 text-center">{{ $t('games') }}</a>
            <a href="#partners" class="hover:underline px-4 py-2 text-center">{{ $t('partners') }}</a>
            <a href="#contact" class="hover:underline px-4 py-2 text-center">{{ $t('contactUs') }}</a>
            <button class="absolute right-5 top-5" @click="toggleMobileMenu"><img src="/images/icon/close.png" alt="Menu" class="w-5 h-5"></button>
            <div class="relative px-4 py-2">
                <div @click="toggleDropdown" class="cursor-pointer flex items-center gap-2">
                    <img :src="currentLang === 'en' ? '/images/united-states.png' : '/images/vietnam.png'" 
                         alt="Flag" class="w-8" /><span class="text-[10px]">&#9660;</span>
                </div>
                <div v-if="showDropdown"
                     class="absolute top-full text-[10px] capitalize right-0 w-35 bg-white text-black border rounded-md shadow-md mt-1">
                    <div @click="changeLanguage('en')"
                        class="flex items-center gap-2 px-4 py-1 cursor-pointer hover:bg-gray-100 hover:rounded-md">
                        <div class="w-[10px]"><span v-show="currentLang == 'en'" >&#10004;</span></div>
                        <img src="/images/united-states.png" alt="English Flag" class="w-6" />
                        English
                    </div>
                    <div @click="changeLanguage('vi')"
                        class="flex items-center gap-2 px-4 py-1 cursor-pointer hover:bg-gray-100 hover:rounded-md">
                        <div class="w-[10px]"><span v-show="currentLang == 'vi'" >&#10004;</span></div>
                        <img src="/images/vietnam.png" alt="Vietnamese Flag" class="w-6" />
                        Tiếng Việt
                    </div>
                </div>
            </div>
        </nav>
    </header>
</template>

<script setup>
import { ref } from 'vue';
import { useI18n } from 'vue-i18n';

const { locale, setLocale  } = useI18n();

const currentLang = ref(locale.value);
const showDropdown = ref(false);
const showMobileMenu = ref(false);

const toggleDropdown = () => {
  showDropdown.value = !showDropdown.value;
};

const changeLanguage = async  (lang) => {
  await setLocale(lang);
  currentLang.value = lang;
  locale.value = lang;
  showDropdown.value = false;
};


const toggleMobileMenu = () => {
  showMobileMenu.value = !showMobileMenu.value;
};
</script>

<style scoped>
.hamburger-menu {
  display: block;
}

.nav-menu {
  display: none;
}

@media (min-width: 768px) {
  .hamburger-menu {
    display: none;
  }
  
  .nav-menu {
    display: flex; 
  }
}
</style>
