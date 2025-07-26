<script setup>
import { ref } from 'vue';
const message = ref("Hello Vue 3")
const space = ref(0)

function spacePressed(){
    space.value++;
    message.value = "Space Pressed " + space.value + " times"
}

function presseKeyName(Event){
    message.value = "You Pressed " + Event.key
}

function buttonPressed(){
    message.value = "You clicked the  button"
}

function ctrlRightClick(){
    message.value = "Ctrl+Right Click"
}

function clickDiv(){
    alert('Only click Div')
}

function clickButton(){
    alert('click Only Button')
}
</script>
<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
        <h2 class="mt-5">{{ message }}</h2>
        <form @submit.prevent action="https://google.com/search">
            <div class="container mx-auto flex space-x-5 jsutify-center m-5">
                <input @keyup.space="spacePressed()" type="text" name="q" class="border border-gray-500 bg-white p-5" placeholder="Enter your Text Hear">
            </div>
            <div class="container mx-auto flex space-x-5 jsutify-center m-5">
                <input @keyup="presseKeyName($event)" type="text" name="text" class="border border-gray-500 bg-white p-5" placeholder="Enter your 2nd Text Hear">
            </div>
            <button @click.prevent="buttonPressed()" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded cursor-pointer">Button</button>
            <button @click.ctrl.right="ctrlRightClick()" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 ml-5 px-4 rounded cursor-pointer">Ctrl + Right Click</button>
        </form>

        <div @click="clickDiv()" class="bg-gray-200 w-[500px] h-80 mt-5 flex items-center justify-center">
            <button @click.stop="clickButton" class="bg-orange-500 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded">
                Button
            </button>
        </div>
    </section>
</template>