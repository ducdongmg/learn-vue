<template>
    <div>
        <input type="text" v-model="newTask">
        <button @click="addTask()">Them</button>
        <div v-for="task in tasks" :key="task.id">
                <input type="checkbox" v-model="task.status" />
            <span :class="{done: task.status}">{{ task.title }} </span> 
        </div>

    </div>
</template>

<script>
export default {
    data() {
        return {
            newTask: '',
            tasks: [
                { title: 'My journey with Vue', status: false },
                { title: 'Blogging with Vue', status: true },
                { title: 'Why Vue is so fun', status: false }
            ]
        }
    },
    methods: {
        addTask: function() {
            this.tasks.push(
                { title: this.newTask, status: false }
            )
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>
