<script>
import axios from 'axios';
import { store } from '../store.js';

export default {
  data() {
    return {
      store,
    }
  },
  methods: {
    search() {
      this.$emit('search');
    }
  }
}
</script>

<template>
  <header class="mb-4 py-5">
    <div class="container">
      <div class="row">
        <div class="col">
          <h1 class="mb-4">
            Rick & Morty App
          </h1>

          <!-- <form @submit.prevent="$emit('search')" class="d-flex justify-content-center"> -->
          <form @submit.prevent="search()" class="d-flex justify-content-center">
            <input v-model="store.name" type="text" class="form-control w-25 me-2" placeholder="Search by name">

            <select v-model="store.status" class="form-select w-25 me-2">
              <option value="">Search by status</option>
              <option value="alive">Alive</option>
              <option value="dead">Dead</option>
              <option value="unknown">Unknown</option>
            </select>

            <button type="submit" class="btn btn-primary me-2">
              Search
            </button>

            <button type="reset" class="btn btn-warning">
              Reset
            </button>
          </form>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

h1 {
  text-align: center;
}
</style>
