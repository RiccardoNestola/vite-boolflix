<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import axios from 'axios';
import { store } from "./store"

export default {
  components: {
    AppHeader,
    AppMain,
  },

  data() {
    return {
      store,
      apiKey: 'dd1c7b6684085e73b6e148e8a93edf44',
      apiUrl: 'https://api.themoviedb.org/3/search/movie',
    }
  },

  methods: {
    getMovies(search) {
      axios.get(this.apiUrl, {
        params: {
          api_key: this.apiKey,
          query: search
          //insert params

        }
      })
        .then((response) => {
          console.log(response.data.results);
          this.store.moviesList = response.data.results;
        })
        .catch(function (error) {
          console.log(error);
        });

    }
  },

  created() {
    /* this.getMovies(); */
  }

}


</script>

<template>

  <AppHeader @inputSearch="getMovies" />

  <AppMain />

</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
