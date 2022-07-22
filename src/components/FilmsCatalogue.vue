<template>
  <div>
    <div class="row pt-4 p-3">
     <div class="col-12">
       <h1>
        Lista dei film
      </h1>
    </div>
    
        <MyFilmCard class="col-2 g-2" v-for="film in films" :key="film.id" :film="film"/>
     </div>
  </div>
</template>

<script>
import MyFilmCard from "./MyFilmCard.vue";


export default {
  name: "FilmsCatatlogue",
  props :["films"]
,
  components: {
    MyFilmCard,
  },

};
</script>

<style></style>
