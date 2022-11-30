<template>
    <div class="card flex-config">
            <img :src="`https://image.tmdb.org/t/p/w300${series.poster_path}`" alt="series images"> 
            <div class="title-container flex-config">
                <h3>
                    {{series.original_name}}
                </h3>
                
                <h3>
                    {{series.original_language.toUpperCase()}}
                </h3>
            </div>
    </div>
    
</template>

<script>


    export default {
        name:"SeriesCards",
        props:{
            series:Object
        },
        
    }
</script>

<style lang="scss" scoped >

.card{
    width: calc(100% / 5);
    height: calc(100% / 2);
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



img{
    width: 70%;
    height:50%;
    margin-top:50px;
    box-shadow: 10px 5px 5px black;
    border-radius: 20px;
    

}
</style>