<script>
import { store } from "../store"

export default {
    name: "AppHeader",

    components: {
    },

    data() {
        return {
            store,
            textSearchOutput: " ",

        }
    },

    methods: {
        searchAll(textSearchOutput) {
            this.$emit('inputSearch', textSearchOutput)
        }
    }

}


</script>

<template>
    <div>
        <h1>header</h1>
        <input type="text" name="" id="" placeholder="Cerca" v-model="textSearchOutput"
            @keyup.enter="searchAll(textSearchOutput)">

        <button @click="searchAll(textSearchOutput)">Cerca</button>
    </div>


</template>

<style lang="scss" scoped>

</style>