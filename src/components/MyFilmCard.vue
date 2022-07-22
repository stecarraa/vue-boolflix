<template>
  <div>
    <div class="card">
      <img
        src="https://cdn1.thespacecinema.it/-/media/tsc/2022/07/thor-love-and-thunder/locandina.jpg?w=400"
        class="card-img-top"
        alt=""
      />
      <div class="card-body">
        <p class="">
          {{film.original_title}}- {{film.title}}- {{film.vote_average}}- {{film.original_language}}
        </p>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "MyFilmCard",

  props:['film']
 

  
};
</script>

<style lang="scss" scoped></style>
