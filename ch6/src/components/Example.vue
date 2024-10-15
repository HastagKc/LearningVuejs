<script setup>
function sayHello() {
  console.log('hello from vue');
}
</script>
<template>
  <!-- syntax  -->
  <!-- v-on:event="method or properties" -->
  <button v-on:click="sayHello">Click</button>
  <!-- shorthand  -->
  <button @click="sayHello">Click2</button>

  
</template>

<style></style>
