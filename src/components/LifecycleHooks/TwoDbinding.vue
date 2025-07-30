<script setup>
import { ref } from 'vue';
const color = ref('None')
function getStyle() {
    return{
        backgroundColor: color.value
    }
    
}
</script>
<template>
    <section class="mx-auto container">
        <h1 class="text-2xl mb-10">Vue Form</h1>
        <p class="pb-b">Your Favorite Color: {{ color }}</p>
        <p>
            Your Favorite Color: 
            <input type="text" class="p-b" v-model="color">
        </p>
        <div class="w-32 h-32 mt-10" :style="getStyle()"></div>
    </section>
</template>