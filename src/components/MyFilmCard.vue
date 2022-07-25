<template>
  <div>
    <!-- <div class="card">
      <img v-if="film.poster_path"
        :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`"
        class="card-img-top"
        alt=""
      />
      <img v-else src="https://www.film-az.com/static/errore-fatale-w342-iRBBZ2gQnk8PAl52MWSpXk7YX4R.jpg" alt="">
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
    </div> -->

    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img
            v-if="film.poster_path"
            :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`"
            class="card-img-top"
            alt=""
          />
          <img
            v-else
            src="https://www.film-az.com/static/errore-fatale-w342-iRBBZ2gQnk8PAl52MWSpXk7YX4R.jpg"
            alt=""
          />
        </div>
        <div class="flip-card-back">
          <h4>{{ film.original_title }}</h4>
          <p>
            <i
              v-for="i in 5"
              :key="i"
              class="fa-star"
              :class="i < returnStars ? 'fa-solid' : 'fa-regular'"
            ></i>
            {{ film.vote_averange }}
          </p>
          <p class="fs-6">{{ film.overview }}</p>
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

.flip-card {
  background-color: transparent;
  width: 300px;
  height: 430px;
  border: 1px solid #f1f1f1;
  perspective: 1000px;
}

img {
  height: 100%;
  width: 100%;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;

  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
}
</style>
