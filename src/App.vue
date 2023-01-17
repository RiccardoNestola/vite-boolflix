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
      apiUrlTv: 'https://api.themoviedb.org/3/search/tv',
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
          console.log(response.data.results + "Films");
          this.store.moviesList = response.data.results;
        })
        .catch(function (error) {
          console.log(error);
        });

    },

    getTvs(searchTv = "harry") {
      axios.get(this.apiUrlTv, {
        params: {
          api_key: this.apiKey,
          query: searchTv
          //insert params

        }
      })
        .then((response) => {
          console.log(response.data.results + "Serie Tv");
          this.store.moviesListTv = response.data.results;
        })
        .catch(function (error) {
          console.log(error);
        });

    },

    getSearch(search) {
      this.getMovies(search),
        this.getTvs(search)
    },



  },



  created() {
    this.getMovies();
    this.getTvs();
  }

}


</script>

<template>


  <AppHeader @inputSearch="getSearch" />





  <AppMain />

</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
