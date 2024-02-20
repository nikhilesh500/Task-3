<template>
    <div>
        <div class="form">
            <form @submit.prevent="submitForm">
                <h1 style="text-align: center">Application Form</h1>
                <input type="text" placeholder="Full Name" v-model="fullName">
                <input type="email" placeholder="Email" v-model="email">
                <input type="text" placeholder="Phone Number" v-model="phone">
                <div class="studies">
                    <input type="text" placeholder="Degree Pursued" v-model="degree">
                    <input type="text" placeholder="Field of Study" v-model="field">
                </div>
                <div class="gender">
                    <h3>Gender: </h3>
                    <input type="radio" id="one" value="Male" v-model="gender" />
                    <label for="one">Male</label>
                    
                    <input type="radio" id="two" value="Female" v-model="gender" />
                    <label for="two">Female</label>
                    
                    <input type="radio" id="three" value="Not to say" v-model="gender" />
                    <label for="three">Prefered Not to say</label>
                </div>
                <div class="cities">
                    <h3>Preffered City:</h3>
                    <select v-model="selected">
                        <option disabled value="">Please select one</option>
                        <option>Amaravati</option>
                        <option>Hyderabad</option>
                        <option>Banglore</option>
                    </select>
                </div>
                <div class="skills">
                    <h3>Skills:</h3>
                    <input type="checkbox" id="HTML" value="HTML" v-model="checkedNames" />
                    <label for="HTML">HTML</label>
                    
                    <input type="checkbox" id="CSS" value="CSS" v-model="checkedNames" />
                    <label for="CSS">CSS</label>
                    
                    <input type="checkbox" id="JavaScript" value="JavaScript" v-model="checkedNames" />
                    <label for="JavaScript">JavaScript</label>
                    
                    <input type="checkbox" id="ReactJs" value="ReactJs" v-model="checkedNames" />
                    <label for="ReactJs">ReactJs</label>
                    
                    <input type="checkbox" id="VueJs" value="VueJs" v-model="checkedNames" />
                    <label for="VueJs">VueJs</label>
                </div>
                <div class="button">
                    <input class="btn" type="submit" value="Apply" /> 
                </div>
            </form>
            <ul class="applies" >
                <h1 style="text-align: center">Application Details</h1>
                <li>Full Name: {{ fullName }}</li>
                <li>Email: {{ email }}</li>
                <li>Phone Number: {{ phone }}</li>
                <li>Degree Pursued: {{ degree }}</li>
                <li>Field of Study: {{ field }}</li>
                <li>Gender: {{ gender }}</li>
                <li>Preffered City: {{ selected }}</li>
                <li>Skills: {{ checkedNames }}</li>
            </ul>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const fullName = ref('')
const email = ref('')
const phone = ref('')
const degree = ref('')
const field = ref('')
const gender = ref('')
const selected = ref('')
const checkedNames = ref([])

const applications = ref([])

const submitForm = () => {
    applications.value.push({ 
        fullName: fullName.value,
        email: email.value,
        phone: phone.value,
        degree: degree.value,
        field: field.value,
        gender: gender.value,
        selected: selected.value,
    });
}
</script>

<style scoped>
    .applies{
        background-color: #42b883d3;
        width: 50%;
        margin: 150px auto;
        border-radius: 15px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    .form {
        width: 100%;
        margin: 0 auto;
        padding: 25px 50px;
        border: 1px solid #ccc;
        border-radius: 15px;
        background-color: #42b88379;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        display: flex;
        gap: 10px;
    }
    form {
        width: 50%;
    }
    input {
        width: 100%;
        margin: 10px auto;
        border-radius: 10px;
        border: 1px solid #aaaaaa;
        padding: 10px 5px ;
        background-color: beige;
    }
    input:focus {
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.225);
        outline: none;
    }
    .studies {
        display: flex;
        gap: 25px;
        margin: 0px auto 10px;
    }
    input[type="radio"], input[type="checkbox"] {
        width: auto;
        background-color: beige;

    }
    .gender, .skills, .cities {
        margin: 15px auto;
    }
    .skills label {
        margin-right: 20px;
        margin-left: 5px;
        font-size: 13px;
    }
    .gender label {
        margin-right: 50px;
        margin-left: 5px;
        font-size: 13px;
    }
    .button {
        display: flex;
        justify-content: center;
    }
    .btn {
        width: 50%;
        border-radius: 5px;
        border: 1px solid #aaaaaa;
        padding: 10px 5px ;
        cursor: pointer;
    }
    .btn:hover {
        background-color: #08b366;
    }
</style>