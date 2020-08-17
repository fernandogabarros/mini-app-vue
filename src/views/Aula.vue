<template>
<div>
  <div v-if="loading">
    <Loading/>
  </div>
  <transition name="fade" mode="out-in">
    <div v-if="api">
      <h2>{{api.nome}}</h2>
      <div class="video">
      <iframe 
      width="560" 
      height="315" 
      :src="`https://www.youtube.com/embed/${api.youtube}`" frameborder="0" 
      allow="accelerometer; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen
      ></iframe>
      </div>
    </div>
  </transition>
</div>
  
</template>

<script>
import fetchData from "@/mixin/fetchData.js"

export default {
  name: 'aula',
  props: ["aula"],
  mixins: [fetchData],
  created() {
    this.fetchData(`aula/${this.aula}`);
  },
  beforeRouteUpdate(to, from, next) {
    this.fetchData(`aula/${to.params.aula}`);
    next();
  }
}
</script>

<style>
.video {
  position: relative;
  padding-bottom: 56.25%
}
.vide iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>