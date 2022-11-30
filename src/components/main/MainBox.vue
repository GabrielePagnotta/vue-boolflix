<template>
    <div class="bg-main">
        <div class="text-title">
            <h2>I miei film:</h2>
        </div>
        
       <div class="flex-config">
        
        <FilmsCards v-for="(el,index) in get" :key="index" :name="el" />
        <div class="text-title">
            <h2>Le mie series:</h2>
        </div>
        <SeriesCards v-for="(el,index) in get2" :key="index" :series="el" />
        
    </div> 
    </div>
    
</template>

<script>
import SeriesCards from "../main/SeriesCards.vue"
import FilmsCards from "../main/FilmsCards.vue"
    export default {
        name:"MainBox",
        props:{
            get: Array,
            get2:Array,
        },
        components:{
            FilmsCards,
            SeriesCards,
        },
        
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