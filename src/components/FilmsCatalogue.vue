<template>
  <div>
    <div class="row pt-4">
      <div class="col-12 mt-3">
        <h1 class="text-white">Lista dei film:</h1>
      </div>
      <MyFilmCard
        class="col-4 g-4"
        v-for="film in films"
        :key="film.id"
        :film="film"
      />
      <div class="col-12  mt-3">
        <h1 class="text-white">Lista delle SerieTv:</h1>
      </div>
      <MySerieCard
        class="col-4 g-3"
        v-for="serie in series"
        :key="serie.id"
        :serie="serie"
      />
    </div>
  </div>
</template>

<script>
import MyFilmCard from "./MyFilmCard.vue";
import MySerieCard from "./MySerieCard.vue";

export default {
  name: "FilmsCatalogue",
  props: ["films", "series"],
  components: {
    MyFilmCard,
    MySerieCard,
  },
};
</script>

<style></style>
