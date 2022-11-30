<template>
    <div class="header-main-box flex-config">
        <div class="flex-config bg-color-red">
            <img class="img-config" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/Netflix_2015_logo.svg/1280px-Netflix_2015_logo.svg.png" alt="">
        </div>
        <div>
            <input class="input-config" type="text" placeholder="Cerca..." v-model="value">
            <button @click="$emit('emitname', value)">Cerca</button>
        </div>
        
    </div>
</template>

<script>
    export default {
        name:"HeaderComp",
        data(){
            return{
                value:"",
            }
        },
        computed:{
            
        },
       
    }
</script>

<style lang="scss" scoped>
.header-main-box{
    width:100%;
    background-color: black;
    color:white;
    padding:20px;
}

.flex-config{
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.img-config{
    width:20%;
    margin-left:50px;
    
    

    
}

.input-config{
    height: 50px;
    font-size: 1.3rem;
    padding-right:100px;
    border: 1px solid red;
    border-radius: 50px;
    background-color: rgb(42, 40, 40);
    
    
}

button{
    height:50px;
    background-color: red;
    border-radius: 20px;
    margin-right:50px;
    margin-left: 10px;
    padding:10px;
    font-size: 1.3rem;
}




</style>