<template>
  <div class="container">
    <FilmsCatalogue :films="films" />
  </div>
</template>

<script>
import FilmsCatalogue from "./FilmsCatalogue.vue";
export default {
  props:{
    'films':Array,
  },
  components: {
    FilmsCatalogue,
  },
};
</script>

<style>
</style>
