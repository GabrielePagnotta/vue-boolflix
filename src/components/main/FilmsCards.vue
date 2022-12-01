<template>
    <div class="card flex-config">
            <img :src="`https://image.tmdb.org/t/p/w300${name.poster_path}`" alt="film images"> 
            <div class="title-container flex-config">
                <h3>
                    {{name.original_title}}
                </h3>
                <h3>
                    {{name.title}}
                </h3>
                <img class="flag" v-if="linguaggio2.includes(name.original_language)" :src="require(`../../assets/${name.original_language}.svg`)" alt="languages">
                <h3 v-else>{{series.original_language}}</h3>
                <h3>
                    {{name.vote_average}}
                </h3>
                <div>
                    <font-awesome-icon v-if="(name.vote_average >2) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(name.vote_average >=4) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(name.vote_average >=6) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(name.vote_average >=8) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />

                    <font-awesome-icon v-if="(name.vote_average >9) " icon="fa-solid fa-star" />
                    <font-awesome-icon v-else icon="fa-regular fa-star" />
                 
                </div>
                
                
            </div>
    </div>
    
   
    

    
</template>

<script>


    export default {
        name:"FilmsCards",
        props:{
            name:Object
        },
        data(){
            return{
                linguaggio2:["it","en","pl","cn","es","fr","ja","pt","nl","de"]
            }
        }
        
    }
</script>

<style lang="scss" scoped >

.card{
    width: calc(100% / 5);
    height: calc(100% / 2);
    margin-top: 20px;
    
}

.flag{
    margin:10px;
    width:20%;
    
}

h3{
    color: white;
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
    width: 95%;
    height:50%;
    margin-top:50px;
    box-shadow: 2px black;
    border-radius: 20px;
    
    

}
</style>