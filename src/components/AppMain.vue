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
    <h1>main</h1>
    <p>
        {{ store.movieList }}
    </p>
</template>

<style lang="scss" >
@use "../styles/general.scss" as *;
@use "../styles/partials/variables.scss" as *;
</style>
