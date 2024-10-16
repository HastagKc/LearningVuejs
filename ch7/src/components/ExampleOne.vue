<script setup>
import { ref, reactive } from 'vue';
const fullName = ref('');

const formData = reactive({
    firstName: '',
    lastName: '',
    address: '',
    hobbies: [],
    gender: '',
    jobPost: '',
});
function formHandler() {
    console.log('Your Form is submitted');
}
</script>
<template>
    <pre>
  {{ formData }}
</pre
    >
    <!-- form in vue js -->
    <!-- v-model is use for form in vue which perform two way binding  -->
    <!-- <p>{{ fullName }}</p>
  <form @submit.prevent="formHandler">
    <input type="text" placeholder="Enter your name" v-model="fullName" />
    <button type="submit">Submit</button>
  </form> -->

    <form @submit.prevent="formHandler">
        <label for="firstName">First Name:</label>
        <input
            type="text"
            name="firstName"
            id="firstName"
            v-model="formData.firstName"
        />
        <br />
        <label for="lastName">Last Name:</label>
        <input type="text" name="lastName" id="lastName" v-model="formData.lastName" />
        <br />
        <label for="address">Address:</label>
        <input type="text" name="address" id="address" v-model="formData.address" />
        <br />
        <span>Multiple Checkbox</span>

        <div>
            <h4>Hobbies</h4>
            <label for="reading">Reading</label>
            <input type="checkbox" v-model="formData.hobbies" value="reading" />

            <label for="writing">Writing</label>
            <input type="checkbox" v-model="formData.hobbies" value="writing" />

            <label for="programming">Programming</label>
            <input type="checkbox" v-model="formData.hobbies" value="programming" />
        </div>

        <br />
        <div>
            <label for="male">Male</label>
            <input type="radio" value="male" id="gender" v-model="formData.gender" />
            <label for="female">Female</label>
            <input type="radio" value="female" id="gender" v-model="formData.gender" />
            <label for="others">Others</label>
            <input type="radio" value="others" id="gender" v-model="formData.gender" />
        </div>
        <br />
        <div>
            <span>
                <label for="jobTitle">Job Post</label>
                <select name="select" id="jobTitle" v-model="formData.jobPost">
                    <option disabled value="">Please Select One</option>
                    <option>Vue js Developer</option>
                    <option>React Developer</option>
                    <option>Angular Developer</option>
                </select>
            </span>
        </div>
        <br />

        <button type="submit">Submit</button>
    </form>
</template>

<style scoped></style>
