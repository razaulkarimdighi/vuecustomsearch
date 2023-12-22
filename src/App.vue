<template>
  <div id="app">
   <h1> {{ title }}</h1>
    <NavbarTop></NavbarTop>
    <CustomSearch></CustomSearch>
  </div>
  
</template>

<script>

import NavbarTop from "./components/NavbarTop.vue"
import CustomSearch from "./components/CustomSearch.vue";

export default {
  name: 'App',
  data(){
    return{
      title: "Hurray! Our vue apps are running!",

    }
  },
  components:{
    NavbarTop,
    CustomSearch
  },
  
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
