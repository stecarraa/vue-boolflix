<template>
  <div class="container">
    <FilmsCatalogue :films="films" :series="series" />
  </div>
</template>

<script>
import FilmsCatalogue from "./FilmsCatalogue.vue";
export default {
  props: {
    films: Array,
    series: Array,
  },
  components: {
    FilmsCatalogue,
  },
};
</script>

<style></style>
