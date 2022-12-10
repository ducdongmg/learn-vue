<template>
  <div>
    <TodoTasks />
  </div>
</template>

<script>
import TodoTasks from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoTasks
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
