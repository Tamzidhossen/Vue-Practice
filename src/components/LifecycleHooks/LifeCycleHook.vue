<script setup>
import { ref, onBeforeMount, onMounted, onUnmounted, onUpdated } from 'vue';
const status = ref([])
const apiResponse = ref(null)

onBeforeMount(()=>{
    console.log('before mount')
    status.value.push('before mount')

    fetch('https://jsonplaceholder.typicode.com/todos/1')
      .then(response => response.json())
      .then(json => {
        apiResponse.value = json
      })
})
onMounted(()=>{
    status.value.push('Mounted')
})
</script>
<template>
    <section class="mx-auto container">
        <h1 class="my-5">Lifecycle Hooks</h1>
        <!-- <div class="flex justify-between mt-20"> -->
            <div class="text-2xl w-1/2">
                {{ status }}
            </div>
            <p class="mt-5">{{ apiResponse }}</p>
        <!-- </div> -->
    </section>
</template>