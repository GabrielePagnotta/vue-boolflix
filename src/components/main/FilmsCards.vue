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
    width: 70%;
    height:50%;
    margin-top:50px;
    box-shadow: 10px 5px 5px black;
    border-radius: 20px;
    border: 5px solid transparent;
    border-image: 1;
    background: linear-gradient(to left,#181717, #960202) border-box;
    

}
</style>