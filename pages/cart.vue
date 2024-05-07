<template>
  <template v-if="cart.length > 0">
    <h1>Ma team </h1>
    <div class="flex flex-row items-center justify-center my-4">
      <div v-for="dish in cart" :key="dish.id" class="flex items-center justify-center space-x-4 my-2 w-full">
        <div class="flex items-center space-x-4">
          <img :src="dish.image" :alt="dish.name" class="w-24 h-24" loading="lazy">
          <p>{{ dish.name }}</p>
        </div>
      </div>
    </div>
  </template>
  <template v-else>
    <div class="flex items-center justify-center my-4">
      <p>Aucun pokemon dans la team</p>
    </div>
  </template>
</template>

<script setup>
const cart = useState('cart')
</script>
