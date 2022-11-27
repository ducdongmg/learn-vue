<template>
  <div>
    <MenuTop />
  </div>
</template>

<script>
import MenuTop from './components/MenuTop.vue'

export default {
  name: 'App',
  components: {
    MenuTop
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
