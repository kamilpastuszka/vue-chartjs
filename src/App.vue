<template>
  <div id="app">
    <graph></graph>
  </div>
</template>

<script>
import Graph from './components/graph';
import Chart from 'chart.js'

export default {
  name: 'App',
  components: {
    Graph
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
