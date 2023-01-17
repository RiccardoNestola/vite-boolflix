<script>
import AppCard from './AppCard.vue'
import { store } from "../store"

export default {
    name: "AppMain",

    components: {
        AppCard
    },

    data() {
        return {
            store,

        }
    }

}

</script>

<template>

    <AppCard />


</template>

<style lang="scss" >
@use "../styles/general.scss" as *;
@use "../styles/partials/variables.scss" as *;
</style>
