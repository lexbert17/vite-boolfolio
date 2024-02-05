<script>
import axios from 'axios';
import { store } from "../store";
    export default{
        data(){
            return{
                store,
            }
        },
        created() {
            axios
            .get(`${this.store.baseUrl}/api/project/${this.$route.params.slug}`)
            .then ((resp)=> {
                
            })
        }
        
    }
</script>

<template>
    <h1>dettagli</h1>
</template>

<style>

</style>