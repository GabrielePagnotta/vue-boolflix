<template>
  <div id="app">
    <!-- header -->
    <HeaderComp  @emitname="searchFilms" />
    <!-- main pricipale -->
    <MainBox :get="arraifilms" :get2="arraiseries" /> 
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
      arraiseries:[],

      
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
      });

      axios.get('https://api.themoviedb.org/3/search/tv?api_key=9ceb8a58ee784657c88b6cb96d573f13&query=' + valoreEmit)
      .then( (response) => {
       this.arraiseries = response.data.results
       
      });

      
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
  background-color: rgb(32, 32, 32);
  
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

::-webkit-scrollbar {
  width: 20px;
}

::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey;
  border-radius: 10px;
}

::-webkit-scrollbar-thumb {
  background: red;
  border-radius: 10px;
}
</style>
