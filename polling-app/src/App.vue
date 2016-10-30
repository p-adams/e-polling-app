<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <register></register>
  </div>
</template>

<script>
import Register from './Register.vue'
export default {
  data () {
    return {
      msg: 'E Polling App'
    }
  },
  components:{
    Register
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
