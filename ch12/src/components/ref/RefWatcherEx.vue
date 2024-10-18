<script setup>
import { ref, watch } from "vue";

const heartRate = ref(75);
watch(heartRate, (newHeartRate, oldHeartRate) => {
  console.log("old heart rate: ", oldHeartRate);
  console.log("new heart rate: ", newHeartRate);

  if (newHeartRate > oldHeartRate && newHeartRate > 120) {
    alert("Your heart rate is increased");
  }
});
</script>

<template>
  <div>
    <h2>Your heart Rate is: {{ heartRate }}</h2>
    <button @click="heartRate -= 5">Decreased</button>
    <button @click="heartRate += 5">Increased</button>
  </div>
</template>

<style scoped></style>
