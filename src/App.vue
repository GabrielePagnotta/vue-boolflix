<template>
  <div id="app">
    <!-- header -->
    <HeaderComp  @emitname="searchFilms"/>
    <!-- main pricipale -->
    <MainBox :get="arraifilms" /> 
  </div>
</template>

<script>
import HeaderComp from "./components/header/HeaderComp.vue";
import MainBox from "./components/main/MainBox.vue"
import axios from "axios"

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainBox,
  },
  data(){
    return{
      
      arraifilms:[],
    }
  },
  mounted(){
    this.searchFilms()
  },
  methods:{
    searchFilms(valoreEmit){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=9ceb8a58ee784657c88b6cb96d573f13&query=' + valoreEmit)
      .then( (response) => {
       this.arraifilms = response.data.results
      })
    },
  
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
