<script setup>
import { ref } from 'vue';
const isActive = ref(false);

setTimeout(() => {
  console.log('set time out is called');
  // to access the value of the ref variable / object we have use .value properties
  isActive.value = true;
}, 2000);
</script>
<template>
  <div>
    <!-- object binding -->
    <!-- <h2 v-bind:class="{ 'text-red': isActive }">Html class Binding</h2> -->
    <h2 :class="{ 'text-red': isActive }">Html class Binding</h2>

    <!-- array to binding multiple class  -->
  </div>
</template>

<style scoped>
.text-red {
  color: red;
}
</style>
