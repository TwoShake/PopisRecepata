<template>
  <div id='app'>
    <navigacija />
    <svastara />
    <slastice/>
    <pica/>
    <futer/>
  </div>
</template>

<script>
import navigacija from './components/navigacija.vue'
import svastara from './components/svastara.vue'
import slastice from './components/slastice.vue'
import pica from './components/pica.vue'
import futer from './components/futer.vue'


export default {
  name: 'App',
  components: {
    navigacija,
    svastara,
    slastice,
    pica,
    futer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

#svastara.box{
    background-image: url("./assets/svastarabg.jpg");
    background-size: 100% 100%;
    height: 600px;
    color:black;
    font-size: xx-large;
}
#slastice.box{
    background-image: url("./assets/pudding.jpg");
    background-size: 100% 100%;
    height: 600px;
    color:black;
    font-size: xx-large;
}
#pica.box{
    background-image: url("./assets/pica.jpg");
    background-size: 100% 100%;
    height: 600px;
    color:black;
    font-size: xx-large;
}
</style>
