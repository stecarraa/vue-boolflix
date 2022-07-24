<template>
  <div>
    <div class="row pt-4 p-3">
      <div class="col-12">
        <h1>Lista dei film</h1>
      </div>
      <MyFilmCard
        class="col-2 g-2"
        v-for="film in films"
        :key="film.id"
        :film="film"
      />
       <div class="col-12">
        <h1>Lista delle SerieTv</h1>
      </div>
       <MySerieCard
        class="col-2 g-2"
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
  props: ["films","serie"],
  components: {
    MyFilmCard,
    MySerieCard,
  },
};
</script>

<style></style>
