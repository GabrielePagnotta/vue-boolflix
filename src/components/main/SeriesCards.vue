<template>
    <div class="card flex-config">
            <img class="posters" :src="`https://image.tmdb.org/t/p/w300${series.poster_path}`" alt="series images"> 
            <div class="title-container flex-config">
                <h3>{{series.language}}</h3>
                <h3>{{series.name}}</h3>
                <h3>{{series.original_name}}</h3>
                <img class="flag" v-if="linguaggio.includes(series.original_language)" :src="`../../assets/${series.original_language}.svg`" alt="languages">
                <h3 v-else>{{series.original_language}}</h3>
                <h3>{{series.vote_average}}</h3>
            </div>
    </div>
    
</template>

<script>


    export default {
        name:"SeriesCards",
        props:{
            series:Object
        },
        data(){
            return{
                linguaggio:["it","en"]
            }
        }
        
    }
</script>

<style lang="scss" scoped >

.card{
    width: calc(100% / 5);
    
    margin-top: 20px;
    
}



.title-container{
    width: 70%;
    padding: 10px;
    border-radius: 10px;
    background-color: rgb(168, 16, 16);
    color:white;
    margin: 20px;  
}
.flex-config{
display: flex;
justify-content: center;
align-items: center;
flex-direction: column;
}



.posters{
    width: 70%;
    height:50%;
    margin-top:50px;
    box-shadow: 10px 5px 5px black;
    border-radius: 20px;
    

}

.flag{
    width:100px;
    height:100px;
}
</style>