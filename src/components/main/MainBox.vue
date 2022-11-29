<template>
    <div class="bg-main">
       <div class="flex-config">
        <FilmsCards/>
        
        
        
        
    </div> 
    </div>
    
</template>

<script>
import FilmsCards from "./FilmsCards.vue"
    export default {
        name:"MainBox",
        components:{
            FilmsCards
        },
    }
</script>

<style lang="scss" scoped >
.box-config{
    width: 80%;
    margin:0 auto;
    
   
    
}
.flex-config{
display: flex;
justify-content: center;
align-items: center;
flex-wrap: wrap;
}


.bg-main{
    background-color: rgb(32, 32, 32);
    height: 100vh;
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