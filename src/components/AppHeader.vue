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
    <header>
        <img src="https://www.freepnglogos.com/uploads/netflix-logo-0.png" alt="netflix logo" class="logo">
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Movies</a></li>
                <li><a href="#">TV Shows</a></li>
                <li><a href="#">Latest</a></li>
                <li><a href="#">My List</a></li>
            </ul>
        </nav>
        <nav>
            <button @click="searchAll(textSearchOutput)">Cerca</button>
            <input type="text" name="" id="" placeholder="Cerca" v-model="textSearchOutput"
                @keyup.enter="searchAll(textSearchOutput)">
        </nav>
    </header>


</template>

<style lang="scss" scoped>
header {
    display: flex;
    align-items: center;
    padding: 16px 5%;
    font-size: 12px;
    background-color: #141414;
}

header img {
    height: 28px;
}

header a {
    text-decoration: none;
    color: white;
    margin-left: 16px;
}

header button {
    background: none;
    color: white;
    border: none;
    margin-right: 16px;
}

nav {
    display: flex;
    align-items: center;
}

nav ul {
    list-style: none;
}

nav li {
    display: inline-block;
}

nav+nav {
    margin-left: auto;
}

.search {
    margin-left: auto;
}

.profile-image {
    width: 40px;
    height: 40px;
    border-radius: 4px;
}
</style>


