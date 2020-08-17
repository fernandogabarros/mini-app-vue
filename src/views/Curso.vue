<template>
<div>
  <div v-if="loading">
    <Loading/>
  </div>
  <transition name="fade" mode="out-in">
  <div v-if="api" class="content">

    <div>
      <h1>{{api.nome}}</h1>
      <p>{{api.descricao}}</p>
      <ul class="aulas">
        <li v-for="aula in api.aulas" :key="aula.id">
          <router-link :to="{name: 'aula', params: {aula: aula.id}}">{{aula.nome}}</router-link>
        </li>
      </ul>
    </div>
    <router-view></router-view>
  </div>
  </transition>
</div>
</template>

<script>
import fetchData from "@/mixin/fetchData.js"

export default {
  name: "curso",
  props: ["curso"],
  mixins: [fetchData],
  created() {
    this.fetchData(`curso/${this.curso}`)
  }
}
</script>

<style>
.aulas li a{
  display: block;
  padding: 20px;
  margin-bottom: 20px;
  border-right: 4px;
  box-shadow: 0 2px 4px rgba(0,0,0,.2);
}
.aulas li a.router-link-active {
  background: #4B8;
  color: white;
}
</style>