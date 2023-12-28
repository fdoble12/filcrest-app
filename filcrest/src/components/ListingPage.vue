<template>
    <Nav/>
    <div id="listing-page" class="py-8">
      <section class="container mx-auto w-full mt-16">
        <h1 class="text-3xl font-bold mb-4">{{ listingData.title }}</h1>
        <div class="relative">
            <carousel ref="myCarousel" :itemsToShow="1" :wrapAround="true" :autoplay="false">
                <slide v-for="(pic, index) in listingData.img" :key="index">
                    <img v-bind:src="pic" class="max-h-full">
                </slide>
            </carousel>
            <button class="absolute left-0 top-1/2 transform -translate-y-1/2 text-white text-xl px-6 hover:text-gray-400" @click="prevSlide">
                <i class="fa fa-chevron-left fa-2x"></i>
            </button>
            <button class="absolute right-0 top-1/2 transform -translate-y-1/2 text-white text-xl px-6 hover:text-gray-400" @click="nextSlide">
                <i class="fa fa-chevron-right fa-2x"></i>
            </button>
        </div>

        <div class="mt-6 border-t-2 border-black pt-2">
            <h1 class="text-3xl font-bold mb-4">P {{ listingData.price }}</h1>
            <p class="mb-4 text-xl">{{ listingData.description }}</p>
            <div class="icon-container flex text-xl justify-start space-x-4 mt-4 text-md text-gray-800">
            <span class="icon"><i class="fa fa-bed" aria-hidden="true"></i> {{ listingData.bedrooms }} Bedrooms</span>
            <span class="icon"><i class="fa fa-shower" aria-hidden="true"></i> {{ listingData.bathrooms }} Bathrooms</span>
            <span class="icon"><i class="fa fa-expand" aria-hidden="true"></i> {{ listingData.floor_area }} sqm</span>
            </div>
        </div>
        <button class="my-4 px-6 py-4 rounded-lg bg-yellow-600">Book a Viewing</button>     
      </section>
    </div>
  </template>
  
  <script>
  import listings from '../assets/listings.json';
  import Nav from './Nav.vue';
  import { Carousel, Slide } from 'vue3-carousel';
  import 'vue3-carousel/dist/carousel.css';
  
  export default {
    name: 'ListingPage',
    props: {
        listingNum: {
            type: String,
            required: true
        }
    },
    data() {
        return {
            listingData: {},
        };
    },
    created() {
        this.fetchListingData();
    },
    methods: {
        fetchListingData() {
            const listing = listings.find(l => l.listing_num.toString() === this.listingNum);
            if (listing) {
                this.listingData = listing;
                console.log(listing.title);
            }
            else {
                // Handle the case where the listing is not found
                console.error('Listing not found');
            }
        },
        nextSlide() {
            this.$refs.myCarousel.next();
        },
        prevSlide() {
            this.$refs.myCarousel.prev();
        }
    },
    components: {
    Nav,
    Carousel,
    Slide
  },
};
  </script>
<style scoped>
</style>
  