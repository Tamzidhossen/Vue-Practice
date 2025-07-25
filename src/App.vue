<template>
  <h1>{{ message }}</h1>
  <h2>Today is <span v-html="date"></span></h2>

  <h1 v-if="location=='Cumilla'">Cumilla</h1>
  <h1 v-if="location=='D'">Dhaka</h1>
  <h1 v-if="location=='C'">Chandpur</h1>
  <h1 v-else>NO Location Found</h1>


  <h1 v-show="location=='Cumilla'">Cumilla</h1>
  <h1 v-show="location=='D'">Dhaka</h1>
  <h1 v-show="location=='C'">Chandpur</h1>
  <h1 v-show="location=='N'">NO Location Found</h1>

  <!-- Part 2 Start -->

  <section class="mx-auto container flex items-center flex-col">
    <div class="space-x-3 justify-center m-5 p-4">
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="changeLocation('Dhaka')">Dhaka</button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="changeLocation('Rajshahi')">Rajshahi</button>
    </div> 
    <h1 class="text-2xl">Current Location is {{ location }}</h1>
  </section>

  <!-- Part 2 end -->

  <!-- Class Binding -->
  <class-binding/>

  <!-- Style Binding -->
  <style-binding/>
  
  <!-- v-for -->
  <v-for/>

  <!-- DisplayTeam -->
  <display-team/>
</template>
<script setup>
  import DisplayTeam from './components/DisplayTeam.vue';
  import vFor from './components/v-for.vue';
  import ClassBinding from './components/ClassBinding.vue';
  import StyleBinding from './components/StyleBinding.vue';
  const message = 'Welcome. Get ready to master Vue. js 3!'
  const date = '<strong>30th June, 2023</strong>'

  // const location = "C";

  import { ref } from 'vue';
  const location = ref('Dhaka')

  function changeLocation(newLocation){
    location.value = newLocation;
  }

</script>