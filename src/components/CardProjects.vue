<script>
export default {
  props: {
    project: Object,
  },
  data() {
    return {
      
    };
  },
  computed: {
    truncateText() {
      if (this.project.content && this.project.content.length > 250) {
        return this.project.content.substring(0, 150) + "...";
      }
      return this.project.content;
    },
  },
};
</script>

<template>
  <div class="card h-100">
    <div class="card-body">
      <h5>{{ project.title }}</h5>
      <span>tipo:
        {{ project.type ? project.type.name : "Nessuna categoria" }}</span>
      <p>{{ truncateText }}</p>
      <router-link :to="{name: 'single-project', params: {slug: project.slug}}">dettagli</router-link>
    </div>
  </div> 
</template>

<style lang="scss" scoped></style>