<script>
import { store } from '../store.js';

import SingleCharacter from './SingleCharacter.vue';

export default {
  data() {
    return {
      store
    }
  },
  components: {
    SingleCharacter
  }
}
</script>

<template>
  <main>

    <div class="container">
      <div class="row">
        <div v-for="(character, i) in store.characters" :key="i" class="col-12 col-sm-6 col-md-3 mb-4">
          <SingleCharacter :character="character" />
        </div>
      </div>
    </div>

  </main>
</template>

<style lang="scss" scoped>
</style>
