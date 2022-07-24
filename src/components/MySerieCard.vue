<template>
  <div>
    <div class="card">
      <img
        :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`"
        class="card-img-top"
        alt=""
      />
      <div class="card-body">
        {{ serie.original_name }}- {{ serie.title }}
        <div>
          <i
            v-for="i in 5"
            :key="i"
            class="fa-star"
            :class="i < returnStars ? 'fa-solid' : 'fa-regular'"
          ></i>
          {{ serie.vote_averange }}
        </div>
        <div>
          <img
            class="flag"
            v-if="language.includes(serie.original_language)"
            :src="require('../assets/' + serie.original_language + '.png')"
            alt=""
          />
          <span v-else> {{ serie.original_language }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      language: ["en", "it", "fr"],
    };
  },

  name: "MySerieCard",

  props: {
    serie: Object,
  },

  computed: {
    returnStars() {
      return Math.ceil(this.serie.vote_average / 2);
    },
  },
};
</script>

<style lang="scss" scoped>
.flag {
  width: 30px;
  height: 15px;
  object-fit: cover;
}
</style>
