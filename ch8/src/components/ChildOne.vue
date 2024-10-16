<script setup>
import { ref, computed } from "vue";
// defining props
// const props = defineProps({
//   fullName: "",
// });

// defining Props
const props = defineProps({
  firstName: "",
  lastName: "",
});

// props are only read-only
// we can not change it directly but we can do it by assinging to local variables
// let fname = ref(props.firstName);
// fname = "Ajay";

// using computed properties
let fullName = computed(() => props.firstName + " " + props.lastName);
</script>
<template>
  <div>
    <!-- using props -->
    <!-- <p>{{ fullName }}</p> -->

    <!-- using props  -->
    <!-- <p>firstName: {{ fname }}</p>
    <p>lastName: {{ lastName }}</p> -->

    <!-- using computed properties -->
    <p>FullName: {{ fullName }}</p>
  </div>
</template>
tempa
<style></style>
