<script>
  import Home from './components/Home.vue';

  export default {
    name: "App",
    components: {
      Home
    }
  }
</script>

<template>
  <Home />
</template>

<style>
  * {
    box-sizing: border-box;
    font-family: 'Open Sans';
  }
  body {
    margin: 0 1em;
    background-image: url('../src/assets/img/0.jpg');
    background-size: 100% 100%;
    min-height: 100vh;
  }
</style>