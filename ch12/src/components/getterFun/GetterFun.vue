<script setup>
import { watch, reactive } from "vue";

// Create a reactive state object
const state = reactive({ heartRate: 75 });

// Watch 'state.heartRate' for changes
watch(
  () => state.heartRate,
  (newHeartRate, oldHeartRate) => {
    console.log("Old Heart Rate: ", oldHeartRate);
    console.log("New Heart Rate: ", newHeartRate);

    if (newHeartRate > oldHeartRate && newHeartRate > 120) {
      console.log("Heart Rate is Increased");
    }
  }
);
</script>

<template>
  <div>
    <h2>Heart Rate: {{ state.heartRate }}</h2>
    <button @click="state.heartRate -= 5">Decrease</button>
    <button @click="state.heartRate += 5">Increase</button>
  </div>
</template>

<style scoped></style>
