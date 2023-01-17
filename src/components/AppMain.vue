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
    <main>
        <AppCard />
    </main>



</template>

<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables.scss" as *;

main {
    width: 90%;
    margin: 2rem auto;
}
</style>
