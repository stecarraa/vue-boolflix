<template>
  <div id="app">
    <MyHeader @getFilms="FindMeSomething"/>
    <MyMainContent :films="films" :series="series"/>
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
        series:[],
        apiKey: '0f0e365597e3faf30d3153696fbdd26d',
        apiUrl:'https://api.themoviedb.org/3/search/',
        query:''
    };
  },
   methods: {

  FindMeSomething(query){
    this.getFilms(query);
    this.getSeries(query);
  },

    getFilms(query) {
      // console.log('recupero i miei film')
      axios
        .get(
          `${this.apiUrl}movie?api_key=${this.apiKey}&query=${query}`
        )
        .then((result) => {
          this.films=result.data.results
                    console.log(this.films);

        })

        .catch((error) => {
          console.warn(error);
        });
    },

     getSeries(query) {
      // console.log('recupero le serie tv')
      axios
        .get(
          `${this.apiUrl}tv?api_key=${this.apiKey}&query=${query}`
        )
        .then((result) => {
          this.series=result.data.results
                    console.log(this.series);

        })

        .catch((error) => {
          console.warn(error);
        });
    },
  },
  
}
</script>

<style lang="scss">
 @import'~bootstrap/dist/css/bootstrap.css'

</style>