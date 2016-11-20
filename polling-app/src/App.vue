<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    {{citizen}}
    <register :states="states"
    >
    </register>
  </div>
</template>

<script>
import Register from './Register.vue'
import States from './States.js'
export default {
  data () {
    return {
      msg: 'E Polling App',
      states: States,
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
