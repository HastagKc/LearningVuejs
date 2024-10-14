<script setup>
// computed properties only for transforming data, for presentation layer.
// They should not alter or change the existing data
import { ref, computed } from 'vue';

// computed properties

let num1 = ref(5);
let num2 = ref(10);
const sum = computed(() => num1.value + num2.value);

setTimeout(() => {
  num1.value = 20;
}, 2000);
</script>
<template>
  <h4>Num1: {{ num1 }}</h4>
  <h4>Num2: {{ num2 }}</h4>
  <h5>Sum: {{ sum }}</h5>
</template>

<style scoped></style>
