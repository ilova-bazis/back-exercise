<template>
  <div id="app">
    
    <div class="container">
      <show-exercises></show-exercises>
    </div>
  </div>
</template>

<script>
import showExercises from './components/showExercises.vue'

export default {
  name: 'app',
  components: {
    'show-exercises': showExercises
  }
}
</script>

<style>
#appss {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
