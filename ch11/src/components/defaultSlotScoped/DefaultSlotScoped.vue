<!-- DefaultSlotScoped.vue -->
<template>
  <div>
    <!-- slot outlet -->
    <!-- Passing 'name', 'job', and 'age' as slot props -->
    <slot :nm="userName" :job="userJob" :age="userAge"></slot>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Define reactive data to pass to the parent through the slot
const userName = ref("John Doe");
const userJob = ref("Software Engineer");
const userAge = ref(30);
</script>

<style scoped>
div {
  border: 1px solid #ccc;
  padding: 10px;
  border-radius: 5px;
}
</style>
