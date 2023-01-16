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
    }

}


</script>

<template>
    <div>
        <h1>header</h1>
        <input type="text" name="" id="" placeholder="Cerca" v-model="textSearchOutput">

        <button @click="$emit('inputSearch', textSearchOutput)">Cerca</button>
    </div>


</template>

<style lang="scss" scoped>

</style>