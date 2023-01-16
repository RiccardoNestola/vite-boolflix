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
      ApiKey: '',
      ApiUrl: '',
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
          this.store.CharactersList = response.data.results;
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
