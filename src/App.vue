<template>
  <div></div>
  <SpeedTest></SpeedTest>
</template>

<script>
import SpeedTest from './components/SpeedTest.vue';
export default {
  name: 'App',
  components: {
    SpeedTest
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
