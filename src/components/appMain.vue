<script>
import axios from 'axios';
export default{
    data(){
        return{
            projects:[]
        }
    },
    created(){
        axios.get('http://127.0.0.1:8000/api/projects')
            .then((resp) => {
                this.projects = resp.data.results.data;
            });
     },
     components: {}
     

}

</script>

<template>
      <div class="container">
    <h2>La lista dei progetti</h2>

    <div class="row row-cols-1 row-cols-md-3 row-cols-lg-4 g-3">
      <div class="col" v-for="project in projects" :key="project.id">
        <PostCars :project="project" />
      </div>
    </div>

  </div>
</template>

<style lang="scss" scoped>

</style>