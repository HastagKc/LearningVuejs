<template>
  <div :class="['base-class', isActive ? 'active' : '', isBold && 'text-bold']">
    This div has an array-based class binding
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isActive = ref(true);
const isBold = ref(false);
</script>
