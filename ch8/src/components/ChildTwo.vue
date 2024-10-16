<script setup>
// Props validation
const props = defineProps({
  names: {
    type: Array,
    required: true,
  },
  employee: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div>
    <p>{{ names }}</p>

    <!-- Iterate over the names array and display each name in an <h3> tag -->
    <h3 v-for="(name, index) in names" :key="index">
      Index:{{ index }} value: {{ name }}
    </h3>

    <h4>{{ employee }}</h4>
  </div>
</template>

<style scoped>
/* Scoped styling to apply only within this component */
h3 {
  color: blue;
  margin: 0.5em 0;
}
</style>
