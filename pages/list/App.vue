<template>
  <div id="app">
    <UIMenu></UIMenu>
  </div>
</template>

<script>
  import UIMenu from './components/Menu'
  export default {
    name: 'app',
    components: {
      UIMenu
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
