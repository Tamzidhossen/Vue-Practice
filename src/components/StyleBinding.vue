<script setup>
    const bgRed = 'background-color: rgba(220, 38, 38, 1)'
    const bgGreen = 'background-color: rgba(5, 150, 105, 1)'

    const colors = {
        borderColor: 'rgba(20, 184, 166, 1)',
        color: 'rgba(19, 78, 74, 1)',
        backgroundColor: 'rgba(204, 251, 241, 1)'
    }

    const Weekday =  false
</script>
<template>
    <section class="mt-10">
        <div class="h-16 flex items-center justify-center text-white" :style="Weekday==true?bgRed:bgGreen">
        It's a Weekday!
        </div>
    </section>
</template>