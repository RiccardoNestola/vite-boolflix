<script>
import { store } from "../store"

export default {
    name: "AppCard",

    components: {
    },

    data() {
        return {
            store

        }
    },

    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/flags/${img}.png`, import.meta.url).href;
        }

    }

}

</script>

<template>
    <main>
        <h1>Film</h1>
        <nav>
            <ul v-for="movies in store.moviesList">
                <li>
                    <p>{{ movies.title }}</p>
                </li>
                <li>
                    <p>{{ movies.original_title }}</p>
                </li>
                <li>
                    <p>{{ movies.vote_average }}</p>
                </li>
                <li>
                    <img :src="getImagePath(movies.original_language)" alt="Country Flag">
                </li>

                <li>
                    <img :src="'https://image.tmdb.org/t/p/w342/' + movies.poster_path" :alt="movies.title">
                </li>
            </ul>
        </nav>

        <h1>TV</h1>

        <nav>
            <ul v-for="tv in store.moviesListTv">
                <li>
                    <p>{{ tv.original_name }}</p>
                </li>
                <li>
                    <p>{{ tv.original_language }}</p>
                </li>
                <li>
                    <p>{{ tv.vote_average }}</p>
                </li>
                <li>
                    <img :src="'https://image.tmdb.org/t/p/w342/' + tv.poster_path" :alt="tv.title">
                </li>
            </ul>
        </nav>






    </main>
</template>

<style lang="scss">

</style>