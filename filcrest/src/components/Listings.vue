<script setup>
import ListingCard from './ListingCard.vue';
</script>
<template>
    <section id="projects" class="border-2 border-black py-16 min-h-[70vh]">
        <div class="container mx-auto">
            <h2 class="text-3xl md:text-4xl text-black font-semibold mb-4">Featured</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <ListingCard/>
                <ListingCard/>
                <ListingCard/>
            </div>
        </div>
    </section>
</template>
<script>
export default {
  name: 'Listings',
};
</script>