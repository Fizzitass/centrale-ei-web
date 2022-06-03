<template>
  <div class="nav">
    <router-link class="nav-link" to="/">Accueil</router-link> |
    <router-link class="nav-link" to="/counter">Counter</router-link> |
    <router-link class="nav-link" to="/users">Users</router-link> |
    <router-link class="nav-link" to="/about">About</router-link>
  </div>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.nav {
  text-align: center;
  padding: 30px;
}

.nav-link {
  font-weight: bold;
  color: #2c3e50;
}

.nav-link.router-link-exact-active {
  color: #42b983;
}
</style>
