<template>
  <header>
    <nav>
      <div class="logo">
        <router-link to="/">Techno</router-link>
      </div>
      <ul>
        <li>
          <router-link to="/cursos">Cursos</router-link>
        </li>
        <li>
          <router-link to="/contato">Contato</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'header'
}
</script>

<style scoped>
  header {
  background: #234;
}
nav {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px 0;
  display: flex;
  align-content: space-between;
}
.logo {
  flex: 1;
}
.logo a, nav a.router-link-exact-active  {
  color: white;
}
nav ul {
  display: flex;
}
nav li {
  margin-left: 20px;
}
nav a {
  font-weight: bold;
  text-decoration: none;
  color: white;
}
ul a.router-link-exact-active {
  color: #42b983;
}
</style>