<template>
  <section class="py-20 bg-gray-800">
    <div class="container mx-auto">
      <h2 class="text-3xl font-bold text-center mb-6">Our Partners</h2>
      <div class="flex flex-wrap justify-center gap-8">
        <img v-for="partner in partners" :key="partner.id" :src="partner.logo" :alt="partner.name" class="h-16" />
      </div>
    </div>
  </section>
</template>

<script setup>
const partners = [
  { id: 1, name: 'Partner 1', logo: '/images/partner1.png' },
  { id: 2, name: 'Partner 2', logo: '/images/partner2.png' },
  { id: 3, name: 'Partner 3', logo: '/images/partner3.png' },
]
</script>
