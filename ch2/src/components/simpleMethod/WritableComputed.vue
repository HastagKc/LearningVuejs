<script setup>
// by default the computed properties is read-only,
// we can make it writable using getter and setter method
// rarely we need writable computed properties

import { ref, computed } from 'vue';

let firstName = ref('Hari');
let lastName = ref('Sharma');
const fullName = computed({
  get() {
    return `${firstName.value} ${lastName.value}`;
  },
  set(newValue) {
    const names = newValue.split(' ');
    firstName.value = names[0];
    lastName.value = names[1];
  },
});

setTimeout(() => {
  firstName.value = 'Krishma';
}, 5000);
</script>
<template>{{ fullName }}</template>

<style scoped></style>
