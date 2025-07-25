<script setup>
    //class Binding
    const bgOrange = "bg-orange-400"
    const bgIndigo = "bg-indigo-400"
    const bgGreen = "bg-green-400"

    const isWeekday = true

    //class Binding Part2
    const colors = {
        bgColor: 'bg-teal-100',
        borderColor: 'border-teal-500',
        textColor: 'text-teal-900'
    }

    const messageType =  "Success";

    if(messageType == 'error'){
        colors.bgColor = 'bg-red-100',
        colors.borderColor = 'border-red-500',
        colors.textColor = 'text-red-900'
    }else if(messageType == 'Success'){
        colors.bgColor = 'bg-teal-100',
        colors.borderColor = 'border-teal-500',
        colors.textColor = 'text-teal-900'
    }else{
        colors.bgColor = 'bg-orange-100',
        colors.borderColor = 'border-orange-500',
        colors.textColor = 'text-orange-900'
    }
</script>
<template>
    <div class="container mx-auto">
        <section class="flex space-x-10">
        <h1 class="w-1/3 h-10" v-bind:class="bgOrange"></h1>
        <h1 class="w-1/3 h-10" :class="bgIndigo"></h1>
        <h1 class="w-1/3 h-10" :class="bgGreen"></h1>
        </section>

        <section class="mt-10">
            <div class="h-16 flex items-center justify-center text-white" :class="isWeekday?'bg-red-600 text-2xl':'bg-green-600 text-4xl'">
            It's a Weekday!
            </div>
        </section>

            <section class="mt-3">
                <div class="border-t-4 rounded-b px-4 py-3 shadow-md" :class="[colors.bgColor, colors.borderColor, colors.textColor]">
                    <p class="font-bold">Our Privacy policy has changed</p>
                    <p class="text-sm">Make sure you know how these changes affect you.</p>
                </div>
            </section>
    </div>

</template>
