<!-- Two Way Data Binding Using Checkbox -->

<script setup>
import { ref, reactive } from 'vue';
const displayImage = ref(true)
</script>
<template>
    <section class="mx-auto container text-center mt-4">
        <h1 class="text-2xl mb-10">Vue Form</h1>
        <p class="mb-10">
            {{ displayImage }}
        </p>
        <label for="">Display Random Image</label>
        <input type="checkbox" class="ml-2" v-model="displayImage">
        <p class="mt-5">
            <input type="radio" name="display" :value="true" v-model="displayImage"> On <br/>
            <input type="radio" name="display" :value="false" v-model="displayImage"> Off <br/>
        </p>
        <img v-show="displayImage" class="mt-10 mx-auto w-[500px] h-[500px]" :src="`https://images.unsplash.com/photo-1753785253859-08113daa0342?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw2NXx8fGVufDB8fHx8fA%3D%3D`" alt="">
    </section>
</template>

<!-- Two Way Data Binding Using Checkbox -->

<!-- <script setup>
import { ref, reactive } from 'vue';
const displayImage = ref(true)
</script>
<template>
    <section class="mx-auto container">
        <h1 class="text-2xl mb-10">Vue Form</h1>
        <p class="mb-10">
            {{ displayImage }}
        </p>
        <label for="">Display Random Image</label>
        <input type="checkbox" class="ml-2" v-model="displayImage">
        <img v-show="displayImage" class="mt-10 mx-auto w-[500px]" :src="`https://unsplash.com/s/photos/random?version=${Math.random()}`" alt="">
        
    </section>
</template> -->

<!-- Two Way Data Binding Using Object -->

<!-- <script setup>
import { reactive } from 'vue';
const person = reactive({
    name: 'Jhon Doe',
    age: 30,
    job: "Software Engineer"
})
</script>
<template>
    <section class="mx-auto container">
        <h1 class="text-2xl mb-10">Vue Form</h1>
        <p class="mb-10">
            {{ person }}
        </p>
        <div class="flex flex-col mb-5 text-left" v-for="(value, key, index) in person" :key="key">
            <label for="">Name</label>
            <input type="text" class="border border-gray-300 rounded-md p-2" v-model="person[key]">
        </div>
    </section>
</template> -->

<!-- Two Way Data Binding Using v-model -->

<!-- <script setup>
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
</template> -->