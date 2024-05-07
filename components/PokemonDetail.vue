<template>
  <div class="m-auto p-4 shadow-lg rounded-lg max-w-md">
    <div v-if="error">
      <p>Erreur lors du chargement des données: {{ error }}</p>
    </div>
    <div v-else-if="pending">
      <p>Chargement des données...</p>
    </div>
    <div v-else>
      <h3 class="text-2xl font-bold text-center">{{ pokemon.name }}</h3>
      <img :src="pokemon.image" :alt="pokemon.name" class="w-64 h-64 mx-auto my-4 aspect-square" loading="lazy">
    
      <button class="w-full text-white uppercase font-semibold bg-red-600 hover:bg-red-700 rounded-full py-2" @click="AddToTeam">
        Ajouter à l'équipe
      </button>
    </div>
  </div>
</template>
  
  <script setup>

import { onMounted, ref } from 'vue'
import { useFetch } from '#app'
const props = defineProps(['pokemon_id'])




const { data: pokemon, pending, error } = useFetch(
  () => `https://pokebuildapi.fr/api/v1/pokemon/${props.pokemon_id}`,
  {
    
  }
)



  
  const counter = ref(0)
  
  const team = useState('team', () => [])
  
  function AddToTeam() {
    if (team.value.length < 6){
      team.value.push(pokemon.value)
    counter.value++
    }
    
  }
  
  </script>
  