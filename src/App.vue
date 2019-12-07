<template>
  <div id="app">
    <img alt="Bone" src="./assets/bone.png" width="30%">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <bonesCalc />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import bonesCalc from './components/bonesCalc'

export default {
  name: 'app',
  components: {
    // HelloWorld,
    bonesCalc
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
