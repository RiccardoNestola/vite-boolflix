<script>
import { store } from "../store"

export default {
    name: "AppMain",

    components: {
    },

    data() {
        return {
            store,

        }
    }

}

</script>

<template>
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
                <p>{{ movies.original_language }}</p>
            </li>
            <li>
                <p>{{ movies.vote_average }}</p>
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
        </ul>
    </nav>

</template>

<style lang="scss" >
@use "../styles/general.scss" as *;
@use "../styles/partials/variables.scss" as *;
</style>
