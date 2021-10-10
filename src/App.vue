<template>
  <home/>
</template>

<script>
import Home from './components/Home.vue'

  export default {
  name:'App',
  components:{
    Home
  }
};
</script>

<style>
/* container */
html,body{
  height: 100%;
}

body {
  background: url("./assets/johannes-plenio-RwHv7LgeC7s-unsplash.png") no-repeat center center
    fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

#app {
  color:#D8D8D8;
  height: 100%;
}
</style>
