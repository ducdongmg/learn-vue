<template>
    <div>

        <h4>What are you favorited?</h4>
        <p v-for="(task, index) in taskList" :key="index" 
            :class=" {choise, selected : task.status}" 
            @click="task.status = !task.status"
        > 
            {{task.title}} 
    </p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTask: '',
            taskList: [
                { title: 'Vue', status: false },
                { title: 'React', status: true },
                { title: 'PHP', status: false }
            ]
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    p {
        border-radius: 5px;
        margin-right: 5px;
        padding: 5px;
        display: inline-block;
        border: 2px solid #0f97a1;
        cursor: pointer;
    }
    .selected {
        background-color: aqua;
    }
</style>
