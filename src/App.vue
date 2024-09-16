<script>
import axios from 'axios';
import { store } from './store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  data() {
    return {
      // store: store,
      store
    }
  },
  components: {
    AppHeader,
    AppMain,
    AppFooter
  },
  methods: {
    performSearch() {
      axios
        .get('https://rickandmortyapi.com/api/character?name=' + this.store.name + '&status=' + this.store.status)
        .then((res) => {
          console.log(res.data.results);

          this.store.characters = res.data.results;
        })
        .catch((err) => {
          console.error(err);

          this.store.characters = [];
        });
    }
  },
  created() {
    this.performSearch();
  }
}
</script>

<template>
  <AppHeader @search="performSearch()" />

  <AppMain />

  <AppFooter />
</template>

<style lang="scss">
@use 'assets/scss/main' as *;
// Import all of Bootstrap's CSS
@import "bootstrap/scss/bootstrap";
</style>
