<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/gaga.png"> -->
    <TelaPrincipal />
  </div>
</template>

<script>
import TelaPrincipal from './components/TelaPrincipal.vue'

export default {
  name: 'App',
  components: {
    TelaPrincipal
  }
}
</script>

<style>
@import url("/assets/styles/destyle.css");

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
