<template>
  <div id="app">
    <h2>E-Polling App</h2>
    <h4>Using Instant Runoff Voting method</h4>
    {{voters}}
    <register v-if="!registered" :states="states"
              :getState="getState"
              :citizenship="getCitizenship"
              :getAge="getAge"
              :firstname="getFirstname"
              :lastname="getLastname"
              :gender="getGender"
              :party="getParty"
              :reg="register"
    >
    </register>
    <vote v-if="registered"></vote>
    
  </div>
</template>

<script>
import Register from './Register.vue'
import States from './States.js'
import Vote from './Vote.vue'
export default {
  data () {
    return {
      voters: [],
      msg: 'E Polling App',
      states: States,
      citizenship: '',
      age: 0,
      firstname: '',
      lastname: '',
      gender: '',
      residence: 'AL',
      party: 'Democrat',
      registered: false
    }
  },
  components:{
    Register,
    Vote
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
    },
    getParty(e){
      this.party = e.target.value
    },
    register(e){
      e.preventDefault()
      if(this.citizenship==='yes' && this.age >= 18){
          this.voters.push({
            citizen: this.citizenship,
            age: this.age,
            firstname: this.firstname,
            lastname: this.lastname,
            res: this.residence,
            party: this.party
          })
          this.registered = !this.registered
      }
    }
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
