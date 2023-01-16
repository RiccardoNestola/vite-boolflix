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
      ApiKey: 'dd1c7b6684085e73b6e148e8a93edf44',
      ApiUrl: 'https://api.themoviedb.org/3/movie/',
    }
  },
  methods: {
    getMovies() {
      axios.get(this.ApiUrl, {
        params: {

          //insert params

        }
      })
        .then((response) => {
          console.log(response.data);
          this.store.getMovies = response.data.results;
        })
        .catch(function (error) {
          console.log(error);
        });

    }
  },

  created() {
    this.getMovies();
  }

}


</script>

<template>

  <AppHeader />

  <AppMain />

</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
