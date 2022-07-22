<template>
    <header>
     <nav class="navbar bg-light">
  <div class="container">
    <a class="navbar-brand">BOOLFLIX</a>
    <form class="d-flex" role="search">
      <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success" type="submit" @click.prevent="">Search</button>
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
            
        }
    }
}
</script>

<style lang="scss" scoped>

</style>