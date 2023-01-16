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
    <nav>
        <ul>
            <li>prima card</li>

        </ul>
    </nav>
</template>

<style lang="scss" >
@use "../styles/general.scss" as *;
@use "../styles/partials/variables.scss" as *;
</style>
