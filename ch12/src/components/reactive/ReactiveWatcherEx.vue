<script setup>
import { reactive, watch } from "vue";

// Create a reactive state object
const state = reactive({ heartRate: 75 });

// Watch the entire 'state' object for changes
// the new and old value will be same because they are referencing same object
// the get old value correctly we have to use getter funciton
watch(state, (newState, oldState) => {
  console.log("Old State: ", oldState.heartRate);
  console.log("New State: ", newState.heartRate);
  if (newState.heartRate > 120) {
    console.log("Your heart Rate is increasing");
  }
});
</script>

<template>
  <div>
    <h2>Heart Rate: {{ state.heartRate }}</h2>
    <button @click="state.heartRate -= 5">Decrease</button>
    <button @click="state.heartRate += 5">Increase</button>
  </div>
</template>

<style scoped></style>
