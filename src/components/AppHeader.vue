<script>
import { store } from "../store"

export default {
    name: "AppHeader",

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
    <h1>header</h1>
    <!-- <input type="text" name="" id="" placeholder="Cerca" v-model="store.textSearchOutput"
        @keyup.enter="$emit('inputSearch', store.textSearchOutput)"> -->

</template>

<style lang="scss" scoped>

</style>