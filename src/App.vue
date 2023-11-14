

<template>
  <div>
    <ThemeGenerator/>
    <FavoriteThemes/>
  </div>

</template>

<script lang="ts">
import ThemeGenerator from './components/ThemeGenerator.vue';
import FavoriteThemes from './components/FavoriteThemes.vue';

export default {
  components: {
    ThemeGenerator,
    FavoriteThemes
  }
}

</script>

<style scoped>

</style>
