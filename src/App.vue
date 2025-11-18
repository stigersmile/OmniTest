<template>
  <div id="app">
    <HelloPage />
  </div>
</template>

<script>
import HelloPage from './components/HelloPage.vue'

export default {
  name: 'App',
  components: {
    HelloPage
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
  margin-top: 60px;
}
</style>
