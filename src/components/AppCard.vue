<script>
import { store } from "../store"

export default {
    name: "AppCard",

    components: {
    },

    data() {
        return {
            store,
            fullVote: [],
            emptyVote: [],


        }
    },

    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/flags/${img}.png`, import.meta.url).href;
        },

        getVote(num) {
            return Math.ceil(num / 2)
        },

    },
    created() {

    }

}

</script>

<template>


    <div class="card-container">



        <div class="card" v-for="movies in store.moviesList">
            <img v-if="movies.poster_path != null" :src="'https://image.tmdb.org/t/p/w342/' + movies.poster_path"
                :alt="movies.title">
            <img v-else src="/not.png" alt="Image Not Available">
            <div class="card-content">
                <h2> {{ movies.title }}</h2>
                <p class="card-hover-text">{{ movies.overview }}</p>



                <div class="card-info">
                    <div class="card-vote">
                        <i v-for="n in getVote(movies.vote_average)" class="fa-solid fa-star"></i>
                    </div>
                    <img class="lang" :src="getImagePath(movies.original_language)" alt="lag">
                </div>
            </div>
            <div class="card-footer">
                <button>Guarda</button>
            </div>
        </div>

        <div class="card" v-for="tv in store.moviesListTv">
            <img v-if="tv.poster_path != null" :src="'https://image.tmdb.org/t/p/w342/' + tv.poster_path"
                :alt="tv.title">
            <img v-else src="/not.png" alt="Image Not Available">
            <div class="card-content">
                <h2> {{ tv.original_name }}</h2>
                <p class="card-hover-text">{{ tv.overview }}</p>



                <div class="card-info">
                    <div class="card-vote">
                        <i v-for="n in getVote(tv.vote_average)" class="fa-solid fa-star"></i>
                    </div>
                    <img class="lang" :src="getImagePath(tv.original_language)" alt="lag">
                </div>
            </div>
            <div class="card-footer">
                <button>Guarda</button>
            </div>
        </div>


    </div>







</template>

<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables.scss" as *;





.card-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.card {
    width: calc(20% - 20px);
    margin-bottom: 20px;
    background-color: #222222;
    border-radius: 10px;
    box-shadow: 0px 0px 10px #000000;
    overflow: hidden;
    position: relative;
}

@media (max-width: 768px) {
    .card {
        width: 100%;
    }
}

.card img {
    width: 100%;
    border-radius: 10px 10px 0px 0px;

}

.card-content {
    padding: 20px;
    color: #ffffff;
    height: 300px;
    overflow: scroll;

}

.card-hover-text {
    display: none;
}

.card:hover .card-hover-text {
    display: block;
}


.card-content h2 {
    font-size: 24px;
    margin-bottom: 10px;
}

.card-content p {
    font-size: 18px;
    margin: 0;

    .desc p {
        display: none;
    }
}



.card-info {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
    padding-bottom: 5rem;
    align-items: center;
}

.card-info p {
    font-size: 1rem;

}

.card-info img {
    width: 60px;
    padding: .5rem;
}

.card-footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 10px;
    background-color: #333333;
    text-align: center;
}

.card-footer button {
    padding: 10px 20px;
    background-color: #ff0000;
    color: #ffffff;
    border: none;
    border-radius: 20px;
    font-size: 16px;
    cursor: pointer;
}
</style>

