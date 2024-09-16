<script>
import { store } from '../store.js';

export default {
  data() {
    return {
      store,
      count: 0
    }
  },
  methods: {
    getAliveNumber() {
      const aliveCharacters = this.store.characters.filter((char) => {
        return char.status.toLowerCase() == 'alive';
      });

      console.log('getAliveNumber');

      return aliveCharacters.length;
    }
  },
  computed: {
    deadNumber() {
      const deadCharacters = this.store.characters.filter((char) => {
        return char.status.toLowerCase() == 'dead';
      });

      console.log('deadNumber');

      return deadCharacters.length;
    }
  }
}
</script>

<template>
  <footer class="py-5">

    <div class="container">
      <div class="row">
        <div class="col text-center">
          <button @click="count++" class="btn btn-primary">
            {{ count }}
          </button>
        </div>
      </div>
    </div>

    <div class="container text-center">
      <div class="row">
        <div class="col">
          <strong>
            Found {{ store.characters.length }} characters
          </strong>
        </div>
      </div>
      <div class="row mt-4">
        <div class="col-12 col-sm-4">
          Found {{ getAliveNumber() }} characters ALIVE
        </div>
        <div class="col-12 col-sm-4">
          Found {{ deadNumber }} characters DEAD
        </div>
        <div class="col-12 col-sm-4">
          Found X characters UNKNOWN
        </div>
      </div>
    </div>

  </footer>
</template>

<style lang="scss" scoped>
</style>
