<template>
    <div class="bg-main">
        <div class="text-title">
            <h2>I miei film:</h2>
        </div>
        
       <div class="flex-config">
        
        <FilmsCards v-for="(elem,index) in arraigenerico" :key="index" :name="elem"/>
        
    </div> 
    </div>
    
</template>

<script>
import axios from"axios"
import FilmsCards from "./FilmsCards.vue"
    export default {
        name:"MainBox",
        components:{
            FilmsCards
        },
        data(){

            return{

                arraigenerico:[]
            }
        },
        mounted(){
            this.arraicicle()
        },
        methods:{
            arraicicle(){
                axios.get('https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=harry+potter')
                .then( (response) => {
                let arraigenerato = response.data.results
                 this.arraigenerico = arraigenerato
                })
            }
        }
    }
</script>


<style lang="scss" scoped >
.box-config{
    width: 80%;
    margin:0 auto;
    
   
    
}
.text-title{
    width:100%;
    margin-left:15px;
    padding:50px;
    text-decoration:underline white;
    
}   
h2{
    color:white;
    font-weight: bold;
    font-size: 2.8rem;
}
.flex-config{
display: flex;
justify-content: center;
align-items: center;
flex-wrap: wrap;
}


.bg-main{
    background-color: rgb(32, 32, 32);
    height: 100%;
}

.card-text-box-2{
    visibility: hidden;
    width:calc(100% / 5);
    height:calc(100%/2);
    border-radius: 100px;
    margin-top:50px;
    background-color: red;
}




</style>