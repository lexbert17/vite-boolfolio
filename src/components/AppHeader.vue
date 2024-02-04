<script>
    export default {
        data(){
            return{
                links: [
                    {
                        name:'home',
                        title: 'Home'
                    },
                    {
                       name:'about',
                       title: 'chi siamo'
                    },
                ]
            }
        }
    }
</script>

<template> 

<nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Boolpress</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation" >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="ms-auto navbar-nav list-unstyled">
          <li class="nav-item" v-for="link in links" :key="link.title">
          <router-link class="text-white gap-5 " :to="{ name: link.name }">{{ link.title }} </router-link>
        </li>
        </ul>
      </div>
    </div>
  </nav>

</template>

<style lang="scss" scoped>

</style>