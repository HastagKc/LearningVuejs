<script setup>
// working with simple method in vue
import { ref } from 'vue';
let firstName = ref('Kshittiz');
let lastName = ref('Chaudhary');

// function fullName() {
//   return firstName.value + ' ' + lastName.value;
// }

// using arrow function
const fullName = () => firstName.value + ' ' + lastName.value;

// checking reactivity

setTimeout(() => {
  firstName.value = 'Hari';
}, 2000);
</script>
<template>
  <h2>{{ fullName() }}</h2>
</template>

<style scoped></style>
