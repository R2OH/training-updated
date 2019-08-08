<template>
  <div id="app">
    <callBox>
    </callBox>
  </div>
</template>

<script>
import callBox from './components/callBox.vue'


export default {
  name: 'app',
  components: {
    callBox
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
  margin-top: 5%;
  min-width: 300px;
}
</style>
