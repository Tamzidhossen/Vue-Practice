<script setup>
    const cnt = [1, 2, 3, 4, 5];
    const tasks = [
        { id: 1, title: "Lorem ipsum dolor sit", status: "completed" },
        { id: 2, title: "Lorem ipsum dolor sit", status: "In Progress" },
        { id: 3, title: "Lorem ipsum dolor sit", status: "Pending" },
        { id: 4, title: "Lorem ipsum dolor sit Abcd", status: "completed" }
    ]

    function getCompletedTasks(){
        return tasks.filter(task => task.status == "completed")
    }
</script>
<template>
    <div class="container">
        <div class="row">
            <!-- <div class="col-12" v-for="(item,index) in tasks" :key="tasks.id">
                <h1> {{ item.id }} - {{ item.title }}</h1>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.</p>
            </div> -->
            <div class="col-12" v-for="(item,index) in getCompletedTasks()" :key="tasks.id">
                <h1> {{ item.id }} - {{ item.title }}</h1>
            </div>
        </div>
    </div>
</template>
