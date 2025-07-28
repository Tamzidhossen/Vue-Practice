<script setup>
import { ref, onMounted } from 'vue';
const items = ref([
    'https://plus.unsplash.com/premium_photo-1672116453187-3aa64afe04ad?q=80&w=869&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    'https://images.unsplash.com/photo-1578589385251-045f05a6faa5?q=80&w=580&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    'https://images.unsplash.com/photo-1578589318274-02854f68813e?q=80&w=580&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    'https://plus.unsplash.com/premium_photo-1680553492268-516537c44d91?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
])

let carosel = null
const newItem = ref('https://images.unsplash.com/photo-1621155346337-1d19476ba7d6?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D')

function addNewItem() {
    items.value.push(newItem.value)
    // carosel.destroy()
    // carosel = new Flickity('.carousel', {})
}

onMounted(()=>{
    carosel = new Flickity('#carosel', {})
})

</script>
<template>
    <!-- <div class="my-10">
        <input type="text" class="border-1 p-1" v-model="newItem">
        <button class="ml-2 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
            Button
        </button>
    </div> -->
    <div class="mx-auto items" id="carosel">
        <div :style="`background-image:url(${item})`" class="item cursor-pointer" v-for="item, index in items" :key="item">{{ index+1 }}</div>
    </div>
</template>
<style  scoped>
    .items{
        width: 600px;
        height: 400px;
    }

    .item{
        width: 600px;
        height: 400px;
        background-color: #ccc;
        background-size: cover;
    }
</style>