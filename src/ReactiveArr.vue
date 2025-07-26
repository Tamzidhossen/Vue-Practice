<script setup>
    import { ref, reactive } from 'vue'
    //Exmple 1
    /*const accordions = reactive([
        false, false, false
    ])

    function toggle(index){
        accordions[index] = !accordions[index]
    }*/
    
    //Exmple 2
    const activeIndex = ref(0)
    const accordions = reactive([
        {
            heading: "What is term",
            content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quod veritatis dolor ipsam illo?",
            isOpen: false
        },
        {
            heading: "When to use Accordion Components?",
            content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quod veritatis dolor ipsam illo?",
            isOpen: false
        },
        {
            heading: "How can  it be defined?",
            content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quod veritatis dolor ipsam illo?",
            isOpen: false
        },
        {
            heading: "Chamber reached  do he nothing  be?",
            content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quod veritatis dolor ipsam illo?",
            isOpen: false
        }
    ])
</script>
<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>

        <div class="w-full p-10 bg-gradient-to-br from-pink-50 to-indigo-100 grid place-items-center">
            <div class="w-3/4 mx-auto rounded border">
                <div class="bg-white p-10 shadow-sm">
                    <h3 class="text-lg font-medium text-gray-800">Several Windows stacked on each other</h3>
                    <p class="text-sm font-light text-gray-600 my-3">
                        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Mollitia qui ullam dolore non, exercitationem dolorum.
                    </p>
                    <div class="h-1 w-full mx-auto border-b my-5"></div>

                    <div class="transition hover:bg-indigo-50" v-for="(accordion, index) in accordions" :key="index">
                        <div @click="accordion.isOpen = !accordion.isOpen" class="accordion-header cursor-pointer transition flex space-x-5 items-center h-16">
                            <i class="fas fa-plus">click</i>
                            <h3>{{ accordion.heading }}</h3>
                        </div>
                        <div class="px-5 pt-0 text-left pb-5" v-show="accordion.isOpen">
                            <p class="leading-6 font-light pl-9">
                                {{ accordion.content }}
                            </p>
                        </div>
                    </div>
                    <!-- <div class="transition hover:bg-indigo-50">
                        <div @click="toggle(1)" class="accordion-header cursor-pointer transition flex space-x-5 items-center h-16">
                            <i class="fas fa-plus">click</i>
                            <h3>Hello2</h3>
                        </div>
                        <div class="px-5 pt-0 text-left pb-5" v-show="accordions[1]">
                            <p class="leading-6 font-light pl-9">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quod veritatis dolor ipsam illo?
                            </p>
                        </div>
                    </div>
                    <div class="transition hover:bg-indigo-50">
                        <div @click="toggle(2)" class="accordion-header cursor-pointer transition flex space-x-5 items-center h-16">
                            <i class="fas fa-plus">click</i>
                            <h3>Hello3</h3>
                        </div>
                        <div class="px-5 pt-0 text-left pb-5" v-show="accordions[2]">
                            <p class="leading-6 font-light pl-9">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quod veritatis dolor ipsam illo?
                            </p>
                        </div>
                    </div> -->
                </div>
            </div>
        </div>
    </section>
</template>