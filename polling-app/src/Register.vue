<template>
    <div class="container">
        <div class="jumbotron">
            <div id="register">
                <h2>Sign Up Form</h2>
                <form>
                    <div class="form-group">
                        <label for="citizenship">Are you a citizen of the United States?</label>
                        <div class="radio">
                            <label><input type="radio"  name="citiz" value="no" @change="citizenship">No</label>
                        </div>
                        <div class="radio">
                            <label><input type="radio"  name="citiz" value="yes" @change="citizenship" checked>Yes</label>
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="age">Age:</label>
                        <input type="text" class="form-control" @input="getAge" placeholder="enter age...">
                    </div>
                    <div class="form-group">
                        <label for="firstname">Firstname:</label>
                        <input type="text" class="form-control" @input="firstname" placeholder="enter firstname...">
                    </div>
                    <div class="form-group">
                        <label for="lastname">Lastname:</label>
                        <input type="text" class="form-control" @input="lastname" placeholder="enter lastname...">
                    </div>
                    <div class="form-group">
                        <label for="gender">Gender</label>
                        <div class="radio">
                            <label><input type="radio" name="gndr" value="female" @change="gender" checked>Female</label>
                        </div>
                        <div class="radio">
                            <label><input type="radio" name="gndr" value="male" @change="gender">Male</label>
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="address">State of residence:</label>
                        <select class="form-control" @change="getState">
                            <option v-for="state in states" :value="state.name">
                                {{state.abbreviation}}
                            </option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="party">Political party:</label>
                        <select class="form-control">
                            <option>Democrat</option>
                            <option>Republican</option>
                            <option>Independent</option>
                        </select>
                    </div>
                    <button @click="register">Register</button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props: [
            'states',
            'getState',
            'citizenship',
            'getAge',
            'firstname',
            'lastname',
            'gender'
            ],
        data(){
            return{
            }
        },
        methods:{
            register: e => {
                e.preventDefault()
            }
        }

    }
</script>