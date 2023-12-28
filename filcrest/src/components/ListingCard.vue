<template>
    <div class="bg-white shadow-md border-2 border-gray-200 flex-col flex rounded-md">
      <div class="mb-4">
        <img
        v-bind:src="listing.img[0]"
          :alt="listing.title"
          class="w-full h-80 object-cover"
        />
      </div>
      <div class="px-4 pb-2">
        <h3 class="text-xl font-semibold mb-2">P {{ listing.price}}</h3>
        <p class="text-black text-lg text-justify">{{ listing.description }}</p>
        <div class="icon-container flex justify-center space-x-3 mt-4 text-md text-gray-800">
          <span class="icon"><i class="fa fa-bed" aria-hidden="true"></i> {{ listing.bedrooms }} Bedrooms</span>
          <span class="icon"><i class="fa fa-shower" aria-hidden="true"></i> {{ listing.bathrooms }} Bathrooms</span>
          <span class="icon"><i class="fa fa-expand" aria-hidden="true"></i> {{ listing.floor_area }} sqm</span>
        </div>
      </div>
      <button
        class="mx-4 my-2 py-2 bg-yellow-800 text-white text-lg rounded-lg"
        @click="goToListingPage"
      >
        See more
      </button>
    </div>
  </template>
  
  <script setup>
    import { useRouter } from 'vue-router';
    
    const props = defineProps({
      listing: Object
    });
    const router = useRouter();
    
    const goToListingPage = () => {
      router.push({ name: 'ListingPage', params: { listingNum: props.listing.listing_num } });
    };
  </script>
  