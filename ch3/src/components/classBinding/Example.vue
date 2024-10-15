<script setup>
import { ref } from 'vue';

const isActive = ref(false);

const toggleBtn = () => {
  isActive.value = !isActive.value;
};
</script>

<template>
  <button :class="isActive ? 'active' : 'inactive'" @click="toggleBtn">
    {{ isActive ? 'Active' : 'Inactive' }}
  </button>
</template>

<style scoped>
button {
  font-size: 16px;
  padding: 5px 10px;
  font-weight: bold;
  width: 90px;
  border-radius: 5px;
}

.active {
  background-color: green;
  color: white;
}

.inactive {
  background-color: red;
  color: white;
}
</style>
