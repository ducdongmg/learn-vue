<template>
    <div>
    <li v-for="task in tasks" :key="task.id">
    {{ task.title }}
    </li>

    </div>
</template>

<script>
export default {
    data() {
        return {
            tasks: [
                { id: 1, title: 'My journey with Vue' },
                { id: 2, title: 'Blogging with Vue' },
                { id: 3, title: 'Why Vue is so fun' }
            ]
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
