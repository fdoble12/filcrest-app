<script setup>
import ListingCard from './ListingCard.vue';
import listings from '../assets/listings.json'; // Assuming listings.json is placed inside the src/assets directory.
</script>
<template>
    <section id="projects" class="border-2 border-black py-16 min-h-[70vh]">
        <div class="container mx-auto">
            <h2 class="text-3xl md:text-4xl text-black font-semibold mb-4">Featured</h2>
            <div class="grid grid-cols-4 gap-6">
                <ListingCard
                    v-for="listing in listings"
                    :key="listing.listing_num"
                    :listing="listing"
                />
            </div>
        </div>
    </section>
</template>
<script>
export default {
  name: 'Listings',
};
</script>