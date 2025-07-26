<script setup>
import { ref, reactive } from 'vue';
const fullImage = ref('https://images.unsplash.com/photo-1613323593608-abc90fec84ff?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTh8fGltYWdlfGVufDB8fDB8fHww')
const images = reactive([
    {
        thumb: "https://images.unsplash.com/photo-1613323593608-abc90fec84ff?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTh8fGltYWdlfGVufDB8fDB8fHww",
        full: "https://images.unsplash.com/photo-1613323593608-abc90fec84ff?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTh8fGltYWdlfGVufDB8fDB8fHww"
    },
    {
        thumb: "https://plus.unsplash.com/premium_photo-1664474619075-644dd191935f?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8aW1hZ2V8ZW58MHx8MHx8fDA%3D",
        full: "https://plus.unsplash.com/premium_photo-1664474619075-644dd191935f?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8aW1hZ2V8ZW58MHx8MHx8fDA%3D"
    },
    {
        thumb: "https://images.pexels.com/photos/31861417/pexels-photo-31861417/free-photo-of-woman-posing-by-ocean-cliffs-at-sunset.jpeg?auto=compress&cs=tinysrgb&w=600&loading=lazy",
        full: "https://images.pexels.com/photos/31861417/pexels-photo-31861417/free-photo-of-woman-posing-by-ocean-cliffs-at-sunset.jpeg?auto=compress&cs=tinysrgb&w=600&loading=lazy"
    }
])
function setImage(val){
    fullImage.value = val.full
}
</script>
<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
        <div class="">
            <div class="flex space-x-2 w-50" >
                <img @click="setImage(image)" class="cursor-pointer" v-for="image in images" :src="image.thumb" :key="image.thumb">
            </div>
            <div class="mt-10">
                <img class="cursor-pointer w-150 h-100 pl-5 mb-7" :src="fullImage" alt="">
            </div>
        </div>
    </section>
</template>