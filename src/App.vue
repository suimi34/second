<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
     <AwesomeForms />
  </div>
</template>

<script>
import AwesomeForms from './components/AwesomeForms.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    AwesomeForms
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
