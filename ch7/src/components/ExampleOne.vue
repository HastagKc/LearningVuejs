<script setup>
import { ref, reactive } from 'vue';
const fullName = ref('');

const formData = reactive({
  firstName: '',
  lastName: '',
  address: '',
});
function formHandler() {
  console.log('Your Form is submitted');
}
</script>
<template>
  <p>FirstName: {{ formData.firstName }}</p>
  <p>LastName: {{ formData.lastName }}</p>
  <p>Address: {{ formData.address }}</p>
  <!-- form in vue js -->
  <!-- v-model is use for form in vue which perform two way binding  -->
  <!-- <p>{{ fullName }}</p>
  <form @submit.prevent="formHandler">
    <input type="text" placeholder="Enter your name" v-model="fullName" />
    <button type="submit">Submit</button>
  </form> -->

  <form @submit.prevent="formHandler">
    <label for="firstName">First Name:</label>
    <input type="text" name="firstName" id="firstName" v-model="formData.firstName" />
    <br />
    <label for="lastName">Last Name: </label>
    <input type="text" name="lastName" id="lastName" v-model="formData.lastName" />
    <br />
    <label for="address">Address:</label>
    <input type="text" name="address" id="address" v-model="formData.address" />
    <br />
    <br />

    <button type="submit">Submit</button>
  </form>
</template>

<style scoped></style>
