<script setup>
import { ref } from 'vue';

// Define a reactive variable for the count
const count = ref(0);

// Define a function to increment the count
const increment = () => {
  count.value++;
};
</script>

<template>
  <div>
    <button @click="increment">clicked: {{ count }}</button>
  </div>
</template>

<style scoped>
/* Add some styles if needed */
button {
  font-size: 16px;
  padding: 10px 20px;
  cursor: pointer;
  /* background-color: #007bff; */
  color: black;
  border: 2px solid black;
  border-radius: 5px;
}

button:hover {
  background-color: #0056b3;
}

h2 {
  font-size: 20px;
  margin-bottom: 15px;
}
</style>
