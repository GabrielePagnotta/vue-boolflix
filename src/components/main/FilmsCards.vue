<template>
    <div class="card flex-config">
        <img v-if="name.poster_path == undefined " class="poster" 
        src="https://www.associazionejam.it/wp-content/uploads/2017/04/non-disponibile-300x300.png" alt="series images"> 
        <img v-else class="poster" :src="`https://image.tmdb.org/t/p/w300${name.poster_path}`" alt="series images">
        <div class="title-container ">
            <h3>Titolo:</h3>
            <h3>{{ name.original_title }}</h3>
            <h3>Titolo reale:</h3>
            <h3>{{ name.title }}</h3>
            <div>
                <h3>lingua:</h3>
                <img class="flag" v-if="linguaggio2.includes(name.original_language)"
                    :src="require(`../../assets/${name.original_language}.svg`)" alt="languages">
                <h3 v-else>{{ series.original_language }}</h3>
            </div>
            <h3>Voto:</h3>
            <h3>{{ name.vote_average }}</h3>
            <div>
                <font-awesome-icon v-if="(name.vote_average > 2)" icon="fa-solid fa-star" />
                <font-awesome-icon v-else icon="fa-regular fa-star" />

                <font-awesome-icon v-if="(name.vote_average >= 4)" icon="fa-solid fa-star" />
                <font-awesome-icon v-else icon="fa-regular fa-star" />

                <font-awesome-icon v-if="(name.vote_average >= 6)" icon="fa-solid fa-star" />
                <font-awesome-icon v-else icon="fa-regular fa-star" />

                <font-awesome-icon v-if="(name.vote_average >= 8)" icon="fa-solid fa-star" />
                <font-awesome-icon v-else icon="fa-regular fa-star" />

                <font-awesome-icon v-if="(name.vote_average > 9)" icon="fa-solid fa-star" />
                <font-awesome-icon v-else icon="fa-regular fa-star" />

            </div>


        </div>
    </div>





</template>

<script>


export default {
    name: "FilmsCards",
    props: {
        name: Object
    },
    data() {
        return {
            linguaggio2: ["it", "en", "pl", "cn", "es", "fr", "ja", "pt", "nl", "de"]
        }
    }

}
</script>

<style lang="scss" scoped >
.card {
    width: calc(100% / 5);
    height: calc(100% / 2);
    margin-top: 20px;
    position: relative;

}

.card:hover .poster {
    -webkit-filter: blur(5px);
    -moz-filter: blur(5px);
    -o-filter: blur(5px);
    -ms-filter: blur(5px);
}

.card:hover .title-container {
    visibility: visible;
    opacity: 90%;
}

.flag {
    margin: 10px 0;
    width: 20%;

}

h3 {
    color: rgb(255, 255, 255);
    font-size: 2rem;
    text-shadow: -1px 0 black, 0 2px black, 1px 0 black, 0 -1px black;
}

.fa-star {
    font-size: 2rem;
    color: yellow;
}

.title-container {
    visibility: hidden;
    width: 80%;
    height: 90%;
    padding: 10px;
    border-radius: 10px;
    margin: 20px;
    position: absolute;
    top: 5%;
    line-height: 50px;


}

.flex-config {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}



.poster {

    width: 80%;
    height: 50%;
    margin-top: 50px;
    box-shadow: 2px black;
    border-radius: 20px;
    box-shadow: 10px 5px 5px black;


}
</style>