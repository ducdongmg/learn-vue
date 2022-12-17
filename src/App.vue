<template>
  <div>
    <TodoTasks v-for="(task, index) in taskList" :key="index" :taskProp1="task" />
  </div>

  
</template>

<script>
import TodoTasks from './components/TaskObj.vue'

export default {
  name: 'App',
  components: {
    TodoTasks
  },
  data() {
    return {
      taskList: [
                { title: 'My journey with Vue', status: false },
                { title: 'Blogging with Vue', status: true },
                { title: 'Why Vue is so fun', status: false }
            ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
