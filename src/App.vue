<script>
import AppProjectMain from './components/AppProjectMain.vue';
 


export default{
  data(){
    return{
       
    }
  },
  components: {  AppProjectMain },
  created(){

  }
}
</script>

<template>

<AppProjectMain />
<router-view></router-view>
</template>

<style lang="scss">
@use "./styles/general.scss" as * ;
</style>

