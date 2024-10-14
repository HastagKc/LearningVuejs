// text interpolation
<script setup>
import { ref } from "vue";
const name = "Kshittiz";
const msg = ref("Good morning, i am kc");
</script>
<template>
  <div>
    <p>{{ msg }}</p>
    <p>{{ name }}</p>
    <p>The current year is {{ new Date().getFullYear() }}.</p>
  </div>
</template>

<style scoped></style>
