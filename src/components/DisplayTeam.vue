<script setup>
    const Person = [
        {
            id: 1,
            name: "Jhon Doe",
            profilePhoto: "https://images.pexels.com/photos/31861417/pexels-photo-31861417/free-photo-of-woman-posing-by-ocean-cliffs-at-sunset.jpeg?auto=compress&cs=tinysrgb&w=600&loading=lazy",
            jobTitle: "CEO, Co-Founder",
        },
        {
            id: 2,
            name: "Jani Doe",
            profilePhoto: "https://plus.unsplash.com/premium_photo-1664474619075-644dd191935f?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8aW1hZ2V8ZW58MHx8MHx8fDA%3D",
            jobTitle: "CTO",
        },
        {
            id: 3,
            name: "Jessy Doe",
            profilePhoto: "https://images.unsplash.com/photo-1613323593608-abc90fec84ff?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTh8fGltYWdlfGVufDB8fDB8fHww",
            jobTitle: "COO",
        }
    ]
</script>
<template>
    <section  class="mx-auto container">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
            <div v-for="person in Person" :key="person.id" class="bg-white rounded-lg shadow-md p-4">
                <img :src="person.profilePhoto" alt="Profile Photo" class="w-full object-cover rounded-md mb-4" :class="person.id == 2?'h-80':'h-60'">
                <h2 class="text-xl font-semibold">{{ person.name }}</h2>
                <p class="text-gray-600">{{ person.jobTitle }}</p>
            </div>
        </div>
    </section>
</template>