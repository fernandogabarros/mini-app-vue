<template>
<div>
  <div v-if="loading">
    <Loading/>
  </div>

  <transition name="fade" mode="out-in">
  <div v-if="api" class="content">

    <div>
      <h1>Sobre a {{api.titulo}}</h1>
      <p>{{api.descricao}}</p>
      <router-link tag="button" to="/cursos" class="bto-course">Cursos</router-link>
      <div class="reviews">
        <h2>Avaliações</h2>
        <ul>
          <li v-for="avaliacao in api.avaliacoes" :key="avaliacao.nome">
            <p>{{avaliacao.nome}}</p>
            <p>{{avaliacao.descricao}}</p>
          </li>
        </ul>
      </div>
    </div>
    <img src="@/assets/img/learn.png" alt="Aprenda Web Design">

  </div>
  </transition>
</div>
</template>

<script>
import fetchData from "@/mixin/fetchData.js"

export default {
  name: 'home',
  mixins: [fetchData],
  created() {
    this.fetchData('home')
  }
}
</script>

<style scoped>
.bto-course {
  cursor: pointer;
  padding: 8px 30px;
  border: none;
  color: white;
  font-weight: bold;
  box-shadow: 0 4px 6px rgba(0,0,0,.2);
  outline: none;
  border-radius: 5px;
  background: #4B8;
  transition: all .3s;
}
.bto-course:hover {
  box-shadow: 0 6px 6px rgba(0,0,0,.2);
}
</style>
