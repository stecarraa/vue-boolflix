<template>
  <div id="app">
    <MyHeader @getFilms="getFilms(query)"/>
    <MyMainContent :films="films"/>
    <MyFooter/>

  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMainContent from './components/MyMainContent.vue'
import MyFooter from './components/MyFooter.vue'

import axios from "axios";

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMainContent,
    MyFooter
  },
   data: function () {
    return {
        films:[],
        apiKey: '0f0e365597e3faf30d3153696fbdd26d',
        apiUrl:'https://api.themoviedb.org/3/search/movie'
    };
  },
   methods: {
    getFilms(query) {
      // console.log('recupero i miei film')
      axios
        .get(
          `${this.apiUrl}?$api_key=${this.apiKey}&query=${query}`
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
}
</script>

<style lang="scss">
 @import'~bootstrap/dist/css/bootstrap.css'

</style>