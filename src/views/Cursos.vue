<template>
<div>
  <div v-if="loading">
    <Loading/>
  </div>

  <transition name="fade" mode="out-in">
  <div v-if="api">
    <div class="content">
      <div>
        <h1>{{api.titulo}}</h1>
        <p>{{api.descricao}}</p>
      </div>

      <ul>
        <li v-for="curso in api.cursos" :key="curso.id">
          <h2>
            <router-link :to="{name: 'curso', params: {curso: curso.id}}">
              {{curso.nome}} - {{curso.totalAUlas}} | {{curso.horas}} horas
            </router-link>
            
          </h2>
          <p>{{curso.descricao}}</p>
        </li>
      </ul>
    </div>
  </div>
  </transition>
</div>
</template>

<script>
import fetchData from "@/mixin/fetchData.js"

export default {
  name: 'cursos',
  mixins: [fetchData],
  created() {
    this.fetchData('cursos')
  }
}
</script>
