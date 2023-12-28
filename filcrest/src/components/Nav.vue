<template>
    <nav class="bg-[#303030] fixed p-4 w-full md:mb-4 lg:mb-6 z-40">
      <div class="container mx-auto flex flex-wrap justify-between items-center">
        <div class="text-white text-2xl md:text-3xl lg:text-2xl mb-2 md:mb-0 font-serif">
          <a href="#hero" class="text-white hover:text-yellow-600" @click="goto">Filcrest Realty</a>
        </div>
        <div class="md:flex items-center space-x-4 md:space-x-6">
          <a href="#listings" class="text-white text-xl md:text-base lg:text-lg hover:text-yellow-600" @click="goto">Listings</a>
          <a href="#" class="text-white text-xl md:text-base lg:text-lg hover:text-yellow-600">Sell</a>
          <a href="#" class="text-white text-xl md:text-base lg:text-lg hover:text-yellow-600">Contact</a>
        </div>
      </div>
    </nav>
  </template>

<script>
    export default {
      name: 'Nav',
    
    };
    
</script>
<script setup>
  import { useRouter } from 'vue-router';
  const router = useRouter();
  const goto = () => {
      router.push({ name: 'Home' });
  };
</script>

<style scoped>
/* Add a custom font family here or link to a font from Google Fonts */
.font-serif {
  font-family: "Roboto", sans-serif;
}
</style>
