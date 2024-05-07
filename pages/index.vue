<template>
  <div class="grid grid-cols-5 w-full gap-4">
    <DishCard v-for="pokemon in pokemons" :key="pokemon.id" :pokemon="pokemon" />
  </div>
</template>

<script setup>
async function fetchData() {
    try {
        const response = await fetch('https://pokebuildapi.fr/api/v1/pokemon/limit/25');
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        const data = await response.json(); 
         
        return data; 
    } catch (error) {
        console.error('There was a problem with the fetch operation:', error);
    }
}
const pokemons = await fetchData();



</script>
