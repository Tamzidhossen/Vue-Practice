<!-- Two Way Data Binding Using dynamic Search -->

<script setup>
import { ref } from 'vue';
import { countries } from '../data/countries';
const search = ref('')

function getFilteredCountries() {
    return countries.filter(country => {
        return country.name.toLowerCase().startsWith(search.value.toLowerCase());
    });
}
</script>
<template>
    <section class="mx-auto container text-center mt-4">
        <h1 class="text-2xl mb-10">Vue Form</h1>
        <p class="mb-10"> {{ search }} </p>
        <p class="mb-5">
            Search: <input type="text" class="px-2 py-1" v-model="search" placeholder="Search Country"/>
        </p>
        <p></p>
        <ul>
            <li v-for="country in getFilteredCountries()" :key="country.code">{{ country.name }}</li>
        </ul>
    </section>
</template>

<!-- Two Way Data Binding Using dynamic context editing -->

<!-- <script setup>
import { ref, reactive } from 'vue';
const persons = reactive([
    { name: 'John Doe', age: 30, email: 'john@doe.com'},
    { name: 'Jane Smith', age: 25, email: 'jane@smith.com'},
    { name: 'Alice Johnson', age: 28, email: 'alice@johnson.com' },
    { name: 'Bob Brown', age: 35, email: 'bob@brown.com' }
])
const activeIndex = ref(0);
</script>
<template>
    <section class="mx-auto container text-center mt-4">
        <h1 class="text-2xl mb-10">Vue Form</h1>
        <p class="mb-10">
            {{ persons }}
        </p>
        <div class="flex">
            <div class="w-1/2">
                <p>{{ activeIndex }}</p>
                <p class="mb-10">
                    <h2>Select a person</h2>
                    <select class="px-2 py-1" name="person" id="person" v-model="activeIndex">
                        <option :value="index" v-for="(person, index) in persons" :key="index">{{ person.name }}</option>
                    </select>
                </p>
            </div>
            <div class="flex flex-col">
                <input type="text" class="my-2 px-2 py-2 border-md" v-for="(value, key, index) in persons[activeIndex]" v-model="persons[activeIndex][key]" :placeholder="key" :key="index"/>
            </div>
        </div>
        
    </section>
</template> -->