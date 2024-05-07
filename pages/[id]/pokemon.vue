<template>
    <div>
      <h1>Pokemon Details</h1>
      <p>ID du Pokémon : {{ pokemonId }}</p>
      <PokemonDetail :pokemon_id="pokemonId" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        
        pokemonId: this.$route.params.id
      };
    },
    
    
  }
  </script>
  