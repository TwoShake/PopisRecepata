<template>
  <div id='app'>
    <navigation />
    <searchbar />
    <apitable />
    <maindishes />
    <sweets/>
    <drinks/>
    <foooter/>
    <carousel/>
  </div>
</template>

<script>
import navigation from './components/navigation.vue'
import maindishes from './components/maindishes.vue'
import sweets from './components/sweets.vue'
import drinks from './components/drinks.vue'
import foooter from './components/foooter.vue'
import carousel from './components/carousel.vue'
import apitable from './components/apitable.vue'
import searchbar from './components/searchbar.vue'

export default {
  name: 'App',
  components: {
    navigation,
    maindishes,
    sweets,
    drinks,
    foooter,
    carousel,
    apitable,
    searchbar
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

#maindishes.box{
    background-image: url("./assets/svastarabg.jpg");
    background-size: 100% 100%;
    height: 600px;
    color:black;
    font-size: xx-large;
}
#sweets.box{
    background-image: url("./assets/pudding.jpg");
    background-size: 100% 100%;
    height: 600px;
    color:black;
    font-size: xx-large;
}
#drinks.box{
    background-image: url("./assets/pica.jpg");
    background-size: 100% 100%;
    height: 600px;
    color:black;
    font-size: xx-large;
}
</style>
