<script setup>
import { ref } from 'vue';
const isActive = ref(false);
const toggle = () => {
  isActive.value = !isActive.value;
};
</script>

<template>
  <button @click="toggle">{{ isActive ? 'active' : 'inactive' }}</button>
</template>

<style scoped>
/* 
Use <style scoped> within your .vue file to apply styles only to that component. 
This ensures styles won’t leak out and affect other components. 

when we don't provide scoped then it will become component level styling
*/
button {
  border-radius: 5px;
  background-color: blue;
  clear: white;
  width: 120px;
  padding: 10px 15px;
  font-size: 16px;
}

.active {
  background-color: green;
  color: black;
}

.inactive {
  background-color: red;
  color: white;
}
</style>
