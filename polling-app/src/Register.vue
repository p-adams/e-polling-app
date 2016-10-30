<template>
    <div id="register">
        <h2>Sign Up Form</h2>
        <form>
            <div class="form-group">
                <label for="citizenship">Are you a citizen of the United States?</label>
                <div class="radio">
                    <label><input type="radio" name="cit">No</label>
                </div>
                <div class="radio">
                    <label><input type="radio" name="cit">Yes</label>
                </div>
            </div>
            <div class="form-group">
                <label for="age">Age:</label>
                <input type="text" placeholder="enter age...">
            </div>
            <div class="form-group">
                <label for="firstname">Firstname:</label>
                <input type="text" placeholder="enter firstname...">
            </div>
            <div class="form-group">
                <label for="lastname">Lastname:</label>
                <input type="text" placeholder="enter lastname...">
            </div>
            <div class="form-group">
                 <label for="gender">Gender</label>
                <div class="radio">
                    <label><input type="radio" name="gender">Female</label>
                </div>
                <div class="radio">
                    <label><input type="radio" name="gender">Male</label>
                </div>
            </div>
            <div class="form-group">
                <label for="address">State of residence:</label>
                <select>
                    <option>Foo</option>
                    <option>Bar</option>
                    <option>Baz</option>
                </select>
            </div>
            <div class="form-group">
                <label for="party">Political party:</label>
                <select>
                    <option>Democrat</option>
                    <option>Republican</option>
                    <option>Independent</option>
                </select>
            </div>
            <button>Register</button>
        </form>
    </div>
</template>

<script>
    export default{

    }
</script>