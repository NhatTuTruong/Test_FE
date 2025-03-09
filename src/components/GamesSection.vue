<template>
  <section class="py-20 bg-gray-700">
    <div class="container mx-auto">
      <h2 class="text-3xl font-bold text-center mb-10">Our Games</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div v-for="game in games" :key="game.id" class="bg-white text-gray-900 p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-bold">{{ game.title }}</h3>
          <p class="text-gray-600">{{ game.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const games = [
  { id: 1, title: 'Game One', description: 'An epic adventure awaits!' },
  { id: 2, title: 'Game Two', description: 'Challenge your friends online.' },
  { id: 3, title: 'Game Three', description: 'Discover new worlds and stories.' },
]
</script>
