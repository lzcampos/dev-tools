<template>
  <header>
    <app-header></app-header>
  </header>
  <main>
    <AppHome />
  </main>
</template>

<script>
import AppHome from './pages/AppHome.vue'
import AppHeader from "./components/AppHeader.vue"
export default {
  name: 'App',
  components: {
    AppHome,
    AppHeader
  }}
</script>

<style>
body {
    margin: 0;
    text-align: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
