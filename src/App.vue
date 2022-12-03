<template>
  <div>
    <TextModel />
  </div>
</template>

<script>
import TextModel from './components/EventHandling.vue'

export default {
  name: 'App',
  components: {
    TextModel
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
