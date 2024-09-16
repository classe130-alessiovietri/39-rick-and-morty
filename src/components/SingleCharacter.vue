<script>
export default {
  data() {
    return {
    }
  },
  props: {
    character: Object
  }
}
</script>

<template>
    <div class="text-center">
        <div>
            <img :src="character.image" :alt="character.name" class="w-100 rounded-circle">
        </div>

        <h3>
            {{ character.name }}
        </h3>

        <h6>
            {{ character.status }}
        </h6>

        <h5>
            {{ character.species }}
        </h5>
    </div>
</template>

<style lang="scss" scoped>
</style>
