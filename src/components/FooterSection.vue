<template>
  <footer class="footer text-white pt-20">
    <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 px-4 text-left">

      <div class="flex flex-col items-start logo">
        <img src="/images/White_logo.png" alt="Logo" class="h-20 mb-10">
        <div class="flex gap-4">
          <a href="#" class="hover:opacity-75"><img src="/images/icon/tw.png" alt="Twitter" class="h-6"></a>
          <a href="#" class="hover:opacity-75"><img src="/images/icon/facebook.png" alt="Facebook" class="h-6"></a>
          <a href="#" class="hover:opacity-75"><img src="/images/icon/in.png" alt="LinkedIn" class="h-6"></a>
        </div>
      </div>

      <div>
        <h3 class="text-2xl font-bold mb-10">{{$t('address')}}</h3>
        <div class="flex items-center gap-5 pb-15">
          <img src="/images/icon/Vector8.png" alt="">
          <p>{{$t('addressDetails1')}}<br>{{$t('addressDetails2')}}</p>
        </div>
        <div class="flex items-center gap-5">
          <img src="/images/icon/Vector6.png" alt="">
          <p>{{$t('contactDetails')}}</p>
        </div>
      </div>

      <div>
        <h3 class="text-2xl font-bold mb-10">{{$t('followUs')}}</h3>
        <p>{{$t('newsletter')}}</p>
        <div class="flex items-center mt-4 border border-white rounded-lg overflow-hidden">
          <input type="email" placeholder="Email" class="bg-transparent w-full px-4 py-2 text-white outline-none">
          <button class=" text-white px-4 py-2 hover:bg-gray-200 hover:text-black cursor-pointer">
            ➔
          </button>
        </div>
      </div>
    </div>
    <div class="text-center mt-8 text-sm bg-black py-5">
      2017 Copyright. Policy.
    </div>
  </footer>
</template>
<style scoped>
.footer {
  color: #fff;
  background-image: url('/images/Bg_footer.png');
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
}

@media (max-width: 768px) {
  .footer .logo {
    align-items: center;
  }
}
</style>