<script setup>
import { ref, reactive, watch } from "vue";

// Reactive properties
const state = reactive({ heartRate: 75 });
const temperature = ref(98.6);
const bloodPressure = reactive({ systolic: 120, diastolic: 80 });

// Watch multiple sources (heartRate, temperature, and bloodPressure)
watch(
  [() => state.heartRate, () => temperature.value, () => bloodPressure.systolic],
  (
    [newHeartRate, newTemperature, newSystolic],
    [oldHeartRate, oldTemperature, oldSystolic]
  ) => {
    console.log("Old Heart Rate:", oldHeartRate, "New Heart Rate:", newHeartRate);
    console.log("Old Temperature:", oldTemperature, "New Temperature:", newTemperature);
    console.log("Old Systolic BP:", oldSystolic, "New Systolic BP:", newSystolic);

    if (newHeartRate > 120) {
      console.log("Warning: Heart rate is too high!");
    }

    if (newTemperature > 100.4) {
      console.log("Warning: High temperature!");
    }

    if (newSystolic > 130) {
      console.log("Warning: High systolic blood pressure!");
    }
  }
);
</script>

<template>
  <div>
    <h2>Heart Rate: {{ state.heartRate }}</h2>
    <h2>Temperature: {{ temperature }}</h2>
    <h2>Blood Pressure: {{ bloodPressure.systolic }}/{{ bloodPressure.diastolic }}</h2>

    <button @click="state.heartRate += 5">Increase Heart Rate</button>
    <button @click="temperature += 0.5">Increase Temperature</button>
    <button @click="bloodPressure.systolic += 5">Increase Systolic BP</button>
  </div>
</template>

<style scoped></style>
