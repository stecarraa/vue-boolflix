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
import axios from "axios";


export default {
  name: "FilmsCatatlogue",

  components: {
    MyFilmCard,
  },

  data: function () {
    return {
        films:[],
    };
  },


   methods: {
    getFilms() {
      // console.log('recupero i miei film')
      axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=0f0e365597e3faf30d3153696fbdd26d&query=300"
        )
        .then((result) => {
          this.films=result.data.results
                    console.log(this.films);

        })

        .catch((error) => {
          console.warn(error);
        });
    },
  },

  created() {
    this.getFilms();
  },
};
</script>

<style></style>
