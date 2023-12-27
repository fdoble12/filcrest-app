<template>

    <!-- Project Card 1 -->
    <div class="bg-white shadow-md border-2 border-gray-200 flex-col flex rounded-md">
        <div class="mb-4">
            <img
                src="../assets/sample.jpeg"
                alt="Project 1"
                class="w-full h-80 object-cover"
            />
        </div>
        <div class="px-4 pb-2">
            <h3 class="text-xl font-semibold mb-2">P 10,000,000</h3>
            <p class="text-black text-lg text-justify">Bungalow in Portofino Heights Las Pinas City</p>
            <div class="icon-container flex justify-center space-x-4 mt-4 text-md text-gray-800">
                <span class="icon"><i class="fa fa-bed" aria-hidden="true"></i> 3 Bedrooms</span>
                <span class="icon"><i class="fa fa-shower" aria-hidden="true"></i> 2 Bathrooms</span>
                <span class="icon"><i class="fa fa-expand" aria-hidden="true"></i> 150 sqm</span>
            </div>
        </div>
        <button class="mx-4 my-2 py-2 bg-yellow-800 text-white text-lg rounded-lg">See more</button>
    </div>

</template>
<script>
export default {
  name: 'ListingCard',
};
</script>