<template>
  <div>
    <div class="card">
      <img
        :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`"
        class="card-img-top"
        alt=""
      />
      <div class="card-body">
        {{ film.original_title }}- {{ film.title }} <div>
          <i
            v-for="i in 5"
            :key="i"
            class="fa-star"
            :class="i < returnStars ? 'fa-solid' : 'fa-regular'"
          ></i>
          {{ film.vote_averange }}
        </div>
        <div>
          <img
            class="flag"
            v-if="language.includes(film.original_language)"
            :src="require('../assets/' + film.original_language + '.png')"
            alt=""
          />
          <span v-else> {{ film.original_language }}</span>
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

  name: "MyFilmCard",

  props: {
    film: Object,
  },

  computed: {
    returnStars() {
      return Math.ceil(this.film.vote_average / 2);
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
