<script setup>
import { ref } from 'vue';
const count = ref(0);

setTimeout(() => {
  console.log(count); // refImp it is ref object
  count.value++; // actual value
}, 3000);
</script>
<template>count: {{ count }}</template>

<style scoped></style>
