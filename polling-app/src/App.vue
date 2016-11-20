<template>
  <div id="app">
    <h2>E-Polling App</h2>
    <h4>Using Instant Runoff Voting method</h4>
    {{gender}}
    <register :states="states"
              :getState="getState"
              :citizenship="getCitizenship"
              :getAge="getAge"
              :firstname="getFirstname"
              :lastname="getLastname"
              :gender="getGender"
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
      citizenship: '',
      age: 0,
      firstname: '',
      lastname: '',
      gender: '',
      residence: 'AL',
      party: ''
    }
  },
  components:{
    Register
  },
  methods:{
    getState(e){
      this.residence = e.target.value
    },
    getCitizenship(e){
      this.citizenship = e.target.value
    },
    getAge(e){
      this.age = e.target.value
    },
    getFirstname(e){
      this.firstname = e.target.value
    },
    getLastname(e){
      this.lastname = e.target.value
    },
    getGender(e){
      this.gender = e.target.value
    }
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
