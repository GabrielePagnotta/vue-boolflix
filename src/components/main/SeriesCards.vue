<template>
    <div class="card flex-config">
            <img class="posters" :src="`https://image.tmdb.org/t/p/w300${series.poster_path}`" alt="series images"> 
            <div class="title-container flex-config">
                <h3>{{series.language}}</h3>
                <h3>{{series.name}}</h3>
                <h3>{{series.original_name}}</h3>
                <img class="flag" v-if="linguaggio.includes(series.original_language)" :src="require(`../../assets/${series.original_language}.svg`)" alt="languages">
                <h3 v-else>{{series.original_language}}</h3>
                <h3>{{series.vote_average}}</h3>
                <div>
                    <font-awesome-icon v-if="(series.vote_average >2) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(series.vote_average >=4) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(series.vote_average >=6) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(series.vote_average >=8) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(series.vote_average >9) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />
                 
                </div>
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
                linguaggio:["it","en","pl","cn","es","fr","ja","pt","nl","de"]
            }
        }
        
    }
</script>

<style lang="scss" scoped >

.card{
    width: calc(100% / 5);
    
    margin-top: 20px;
    
}


.fa-star{
font-size: 2rem;
color: yellow;
}
.title-container{
    width: 70%;
    padding: 10px;
    border-radius: 10px;
    background-color: rgb(168, 16, 16);
    color:white;
    margin: 20px;  
    border: 5px solid transparent;
    border-image: 1;
    background: linear-gradient(to left,#000000, #960202) border-box;
    
}
.flex-config{
display: flex;
justify-content: center;
align-items: center;
flex-direction: column;
}






img{
    width: 100%;
    height:50%;
    margin-top:50px;
    box-shadow: 10px 5px 5px black;
    border-radius: 20px;
    
}
.flag{
    margin:10px;
    width:20%;
    
}
</style>