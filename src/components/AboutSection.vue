<template>
  <div class="about-us py-10 px-10 mx-auto grid grid-cols-1 md:grid-cols-2 gap-10 max-w-[1200px] text-left relative">
    <div class="bonus hidden">
      <img class="z-2 mt-[-200px] max-w-[350px] mx-auto h-auto object-cover" src="/images/Fairy.png" alt="">
    </div>
    <div>
      <h2 class="text-4xl font-bold mb-4 text-black font-playfair">{{$t('aboutUs')}}</h2>
      <p class="mb-12 text-gray-600">
        {{$t('des_about')}}
      </p>
      <div class="mb-4">
        <span class="text-[50px] font-bold text-[#079BEE]">600<span class="text-[20px]">M</span>+</span>
        <span class="block text-lg text-black">{{$t('users')}}</span>
      </div>
      <div>
        <span class="text-[50px] font-bold text-[#079BEE]">135+</span>
        <span class="block text-lg text-black">{{$t('games')}}</span>
      </div>
    </div>

    <div class="bg-gray-100 p-12 rounded-lg text-black">
      <div class="mb-4">
        <h3 class="font-bold text-lg flex items-center">
          <span class="p-2 rounded-full mr-2"><img class="w-15" src="/images/icon/Group 12.png" alt=""></span>
          {{$t('24Hour')}}
        </h3>
        <p class="text-gray-600 text-left">{{$t('24HourDescription')}}</p>
      </div>
      <div class="mb-4">
        <h3 class="font-bold text-lg flex items-center">
          <span class="p-2 rounded-full mr-2"><img class="w-15" src="/images/icon/Group 13.png" alt=""></span>
          {{$t('design')}}
        </h3>
        <p class="text-gray-600 text-left">
          {{$t('designDescription')}}
        </p>
      </div>
      <div>
        <h3 class="font-bold text-lg flex items-center">
          <span class="p-2 rounded-full mr-2"><img class="w-15" src="/images/icon/Group 14.png" alt=""></span>
          {{$t('team')}}
        </h3>
        <p class="text-gray-600 text-left">
          {{$t('teamDescription')}}
        </p>
      </div>
    </div>
  </div>
  <div class="w-full max-w-[1100px] mx-auto flex flex-col items-center px-4">
    <img src="/images/Illustrator.png" 
         alt="Witch Character" 
         class="w-48 sm:w-60 md:w-72 mb-4 animate-move" />
    <img src="/images/Pin-map.png" alt="Map Illustration" class="w-full" />
</div>
</template>

<script setup>
</script>

<style scoped>
.about-us {
  background-color: #fff;
}

@keyframes move {
    0% { transform: translateX(0); }
    25% { transform: translateX(150px); }
    50% { transform: translateX(0); }
    75% { transform: translateX(-150px); }
    100% { transform: translateX(0); }
}

.animate-move {
    animation: move 5s ease-in-out infinite; 
}

@media (max-width: 768px) {
  .bonus {
    display: block;
  }
}
</style>