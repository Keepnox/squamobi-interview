<template>
  <div id="app">
    <smartphone>
      selam
    </smartphone>
  </div>
</template>

<script>
import Smartphone from './components/Smartphone.vue'
export default {
  name: 'App',
  components: {Smartphone}
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
