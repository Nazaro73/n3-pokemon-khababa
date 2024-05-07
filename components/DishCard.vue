<template>
  <div class="max-w-lg mx-auto my-8 p-4 shadow-lg rounded-lg">
    <img :src="pokemon.image" :alt="pokemon.name" class="w-64 h-64 mx-auto" loading="lazy">
    <div class="text-center mt-4">
      <h3 class="text-xl font-semibold">{{ pokemon.name }}</h3>
      <NuxtLink :to="`/${parseInt(pokemon.id)}/pokemon`" class="mt-4 inline-block bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Voir Pokémon
      </NuxtLink>
    </div>
  </div>
</template>


<script setup>
const props = defineProps(['pokemon'])



</script>
