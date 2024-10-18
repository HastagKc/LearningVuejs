<script setup>
// The v-for directive can also be used to iterate over a range of numbers. This is particularly useful when you want to render a set number of elements or need to display something a specific number of times.
</script>
<template>
  <ul>
    <li v-for="n in 5" :key="n">
      {{ n }}
    </li>
  </ul>
</template>

<style></style>
