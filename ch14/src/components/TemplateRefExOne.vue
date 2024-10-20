<script setup>
import { ref, onMounted } from 'vue';

// Create a reactive ref for the input element
const inputRef = ref(null);

onMounted(() => {
  // Logs the input DOM element
  console.log(inputRef.value);
  // Focus the input element on mount
  if (inputRef.value) {
    inputRef.value.focus();
  }
});
</script>

<template>
  <div>
    <label for="username">Username: </label>
    <!-- Assign the ref directly to the input element -->
    <input type="text" name="username" id="username" ref="inputRef" />
  </div>
</template>

<style scoped></style>
