<template>
    <header>
     <nav class="navbar bg-dark">
  <div class="container">
    <a class="navbar-brand text-danger fw-bolder fs-1">BOOLFLIX</a>
    <form class="d-flex" role="search">
      <input class="form-control me-2" type="search" placeholder="Search a title..." aria-label="Search" v-model="query"  @keyup="$emit('getFilms', query)" >
      <button class="btn btn-outline-danger" type="submit" @click.prevent="$emit('getFilms', query)" >Search</button>
    </form>
  </div>
</nav>
    </header>
</template>

<script>
export default {
    name:'MyHeader',
    
    data(){
        return{
            query:''
        }
    }
}
</script>

<style lang="scss" scoped>

</style>