<template>
    <div class="header-main-box flex-config">
        <div class="flex-config bg-color-red">
            <img class="img-config" src="https://www.giuseppecaprotti.it/2019/wp-content/uploads/Netflix-Logo.png" alt="">
        </div>
        <div>
            <input class="input-config" type="text" placeholder="Cerca...">
        </div>
        
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.header-main-box{
    width:100%;
    background-color: black;
    color:white;
}

.flex-config{
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.img-config{
    width:35%;
    margin-left:50px;
    
}

.input-config{
    height: 40px;
    padding-right:100px;
    border: 1px solid red;
    border-radius: 50px;
    background-color: rgb(42, 40, 40);
    
    
}




</style>