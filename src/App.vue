<template>
  <Indecision/>

</template>

<script>
import Indecision from './components/Indecision.vue'
import Contador from './components/Contador.vue'

export default {
  name: 'App',
  components: {
    Contador,
    Indecision
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
