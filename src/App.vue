<template>
  <Home/>
  <div id="nav">
    <router-link to="/">Home</router-link>
    |
    <router-link to="/snippet">Snippet</router-link>
  </div>
  <router-view/>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    Home
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
