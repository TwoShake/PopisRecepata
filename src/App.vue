<template>
  <div id='app'>
  <navigacija />
  
  </div>
</template>

<script>
import navigacija from './components/navigacija.vue'

export default {
  name: 'App',
  components: {
    navigacija
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
  background-color: black;
}
navigacija{
  background-color: black;
}
</style>
