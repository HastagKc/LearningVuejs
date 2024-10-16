<script setup>
import { ref } from "vue";
const props = defineProps({
  name: String,
  employeeType: String,
});
</script>
<template>
  <div>
    <h3>Name: {{ name }}</h3>
    <h4>Employee Type: {{ employeeType }}</h4>
  </div>
</template>

<style></style>
