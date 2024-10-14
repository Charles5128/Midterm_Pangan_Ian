<template>
  <div id="app">
    <header>
      <h1>Charles Ian Pangan</h1>
      <h2>BSIT - 3</h2>
      <nav>
        <router-link to="/home">Home</router-link>
        <router-link to="/products">Products</router-link>
      </nav>
    </header>
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

header {
  background-color: #f8f9fa;
  padding: 10px;
}

nav {
  margin: 20px 0;
}

nav a {
  margin: 0 15px;
  text-decoration: none;
  color: #42b983; /* Change color as desired */
}

nav a.router-link-exact-active {
  font-weight: bold;
}
</style>
