<template>
  <div>
    <div class="card">
      <img
        src="https://cdn1.thespacecinema.it/-/media/tsc/2022/07/thor-love-and-thunder/locandina.jpg?w=400"
        class="card-img-top"
        alt=""
      />
      <div class="card-body">
       
          {{serie.original_title}}- {{serie.title}}- {{serie.vote_average}}-
          <div>
                        <img class="flag" v-if="language.includes(serie.original_language)" :src="require('../assets/' + serie.original_language + '.png')" alt="">
                        <span v-else> {{serie.original_language}}</span>
                    </div>
        
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data(){
        return{
            language:['en','it','fr'],
        }
    },

  name: "MySerieCard",

props:{
        'serie':Object
    }, 

  
};
</script>

<style lang="scss" scoped>
.flag{
    width: 30px;
    height: 15px;
    object-fit: cover;
}
</style>
