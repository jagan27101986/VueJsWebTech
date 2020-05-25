<template>
  <div id="app">
    <Courses></Courses>
  </div>
</template>

<script>
import Courses from './components/Courses.vue'

export default {
  name: 'App',
  components: {
    Courses
  }
}
</script>

<style>
#app {
    font-family: roboto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: grid;
  max-width:1200px;
  margin:20px auto;
  height:100%;
  overflow-x:none;
}
</style>
