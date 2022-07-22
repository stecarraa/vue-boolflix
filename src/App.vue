<template>
  <div id="app">
    <MyHeader @search="doSearch" />
    <MyMainContent :films="films" :series="series"/>

  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMainContent from './components/MyMainContent.vue'
import axios from "axios";

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMainContent
  },
  data(){
    return{
      films:[],
      series:[],
      myKey:'0f0e365597e3faf30d3153696fbdd26d',
      language:'it-IT'
    }
  },
  methods:{
    doSearch(keyword){
      const params={
          params:{
            'api_key':this.apy_key,
            'query':keyword,
            'language':this.language
          }
        };
        this.getFilms(params);
        
    },
    getFilms(params) {
        axios.get('https://api.themoviedb.org/3/search/movie/' , params)
        
        .then((response) => {
            this.films = response.data.results;
    
          })
        .catch(function (error) {
            
            console.log(error);
        });
        
    },
    
  }
}
</script>

<style lang="scss">
  
</style>