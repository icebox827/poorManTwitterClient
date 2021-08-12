<template>
  <Navbar />
  <Tweet />
</template>

<script>
import Navbar from './components/Navbar.vue'
import Tweet from './components/Tweet.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Tweet
  }
}
</script>

<style>
#app {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
