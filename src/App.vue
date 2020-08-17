<template>
  <div id="app">
    <Header/>
    <router-view class="container"></router-view>
  </div>
</template>


<script>
import Header from "@/components/Header.vue"
export default {
  components: {
    Header
  }
}
</script>


<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px 0;
}
img {
  max-width: 100%;
}
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
.content {
  display: grid;
  grid-template-columns: 1fr minmax(200px, 400px);
  gap: 20px;
}
@media screen and (max-width: 680px) {
  .content {
    display: block;
  }
  img {
    width: 400px;
  }
}
.fade-enter, 
.fade-leave-to {
  opacity: 0;
  transform: translate3d(0,-20px,0)
}
.fade-enter-active,
.fade-leave-active {
  transition: all .4s;
}
</style>
