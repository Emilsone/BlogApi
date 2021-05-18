<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <BlogApi/>
  </div>
</template>

<script>
import BlogApi from './components/BlogApi.vue'

export default {
  name: 'App',
  components: {
   BlogApi
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');
#app {
 font-family: 'Rubik', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   background: #313131;
height: 100vh;
font-size:18px;

}
*{
padding:0px;
margin: 0px;
}
</style>
