<template>
<div>
  <img alt="Vue logo" src="./assets/scrabble.jpg">
  <Solver></Solver>
</div>
</template>

<script>
import Solver from './components/Solver.vue'

export default {
  name: 'App',
  components: {
    Solver,
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
