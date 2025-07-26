<script setup>
import { ref } from 'vue';
const about = ref("Hello")
const links = [
    {
        name: "Google",
        url: "https://www.google.com",
        about: "Google Link Lorem ipsum, dolor sit amet consectetur adipisicing."
    },
    {
        name: "FaceBook",
        url: "https://www.facebook.com",
        about: "Facebook Link Lorem ipsum, dolor sit amet consectetur adipisicing."
    },
    {
        name: "Microsoft",
        url: "https://www.microsoft.com",
        about: "Microsoft Link Lorem ipsum, dolor sit amet consectetur adipisicing."
    },
    {
        name: "Twitter",
        url: "https://www.Twitter.com",
        about: "Twitter Link Lorem ipsum, dolor sit amet consectetur adipisicing."
    }
]
function setText(element){
    about.value = element
}
</script>
<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
        <h2 class="mt-5">{{ about }}</h2>
        <div class="container mx-auto flex space-x-5 justify-center m-[1000px]">
            <a @click.prevent="setText(link.about)" v-for="link in links" :key="link.name" href="#">{{ link.name }}</a>
        </div>
    </section>
</template>
