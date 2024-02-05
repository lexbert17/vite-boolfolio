<script>
import axios from 'axios';
import { store } from "../store";
    export default{
        data(){
            return{
                store,
                project: null,
                loading: false
            };
        },
        created() {
            this.loading = true;
            axios
            .get(`${this.store.baseUrl}/api/projects/${this.$route.params.slug}`)
            .then ((resp) => {
                console.log(resp.data);
                if(resp.data.success) {
                    this.project = resp.data.results;
                }else{
                    console.log(this.$router);
                    this.$router.push({name: 'not-found'})
                }  
            })
            .finally(()=> {
                this.loading = false
            });
        },
        
    };
</script>

<template>
    <h1>dettagli</h1>

    <div class="container mt-4">
    <div v-if="loading">
      Caricamento...
    </div>
    <div v-else>
      <h1>{{ project.title }}</h1>
      <div>
        tecnologia: {{ project.technologies.name }}
      </div>
      <div>
        tipologia: {{ project.type.name }}
      </div>
      <div>
        Pubblicato: {{ project.created_at }}
      </div>
      <div class="my-3">
        <span class="me-2 p-2" :style="{'background-color': tag.hex_color}" v-for="tag in project.types">{{ tag.name }}</span>
      </div>
      <p>{{ project.content }}</p> 
    </div>
  </div>
</template>

<style>

</style>