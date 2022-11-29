<template>
    <div class=" card flex-config">
            <img src="https://www.ilpost.it/wp-content/uploads/2019/12/locandine14.jpg?x48908" alt="">    
    </div>
    
   
    

    
</template>

<script>
    export default {
        name:"FilmsCards"
    }
</script>

<style lang="scss" scoped >

.card{
    width: calc(100% / 5);
    height: calc(100% / 2);
    margin-top: 20px;
    
}


.flex-config{
display: flex;
justify-content: center;
align-items: center;
}



img{
    width: 70%;
    height:50%;
    margin-top:50px;
    box-shadow: 10px 5px 5px black;
    

}
</style>