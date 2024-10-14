<script setup>
import { reactive, ref } from 'vue';
const activeColor = ref('green');
const textSize = ref(32);

// style binding to object
// here in the object binding the key should be valid  CSS properties
const styleObj = reactive({
  color: 'black',
  backgroundColor: 'green',
});

const styleObj2 = reactive({
  fontSize: '50px',
});
</script>
<template>
  <!-- Binding inline style -->
  <h2 v-bind:style="{ color: 'red', backgroundColor: 'blue' }">Binding Inline Style</h2>
  <h2 :style="{ color: 'red', backgroundColor: 'blue' }">Binding Inline Style2</h2>

  <!-- Using reactive variable  -->
  <h2 :style="{ color: activeColor, fontSize: textSize + 'px' }">Reactive variable</h2>

  <!-- binding using object -->
  <h2 :style="styleObj">This is object Binding</h2>

  <!-- binding multiple inline style using array -->
  <h2 :style="[styleObj, styleObj2]">binding multiple inline style using array</h2>
</template>

<style scoped></style>
