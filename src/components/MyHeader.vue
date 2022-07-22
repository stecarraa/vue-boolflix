<template>
    <header>
     <nav class="navbar bg-light">
  <div class="container">
    <a class="navbar-brand">BOOLFLIX</a>
    <form class="d-flex" role="search">
      <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" v-model="query">
      <button class="btn btn-outline-success" type="submit" @click.prevent="$emit('getFilms', query)" >Search</button>
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