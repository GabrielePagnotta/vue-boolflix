<template>
  <div id="app">
    <!-- header -->
    <HeaderComp />
    <!-- main pricipale -->
    <MainBox /> 
  </div>
</template>

<script>
import HeaderComp from "./components/header/HeaderComp.vue";
import MainBox from "./components/main/MainBox.vue"

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainBox,
  },
  Data(){
    return{
      arraifilm:[],
    }
  },
  mounted(){

  },
  method:{
    
  },
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  input::placeholder { 
  color: white;
  }
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
