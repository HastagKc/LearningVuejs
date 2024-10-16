<script setup>
import { ref } from "vue";

//childOne
import ChildOne from "./components/ChildOne.vue";
// ChildTwo
import ChildTwo from "./components/ChildTwo.vue";

import ChildThree from "./components/ChildThree.vue";

const firstName = ref("Aasish");
const lastName = ref("Chaudhary");

// Binding multiple properties using object
const employee = {
  name: "Arab",
  employeeType: "Manager",
};
</script>

<template>
  <!-- childOne -->
  <!-- passing props value -->
  <!-- static props  -->
  <!-- <ChildOne fullName="Kshittiz Chaudhary" /> -->

  <!-- dynamic props -->
  <!-- for passing dynamic props we have to use v-bind directive or shorthand (:) -->

  <!-- <ChildOne :firstName="firstName" :lastName="lastName" /> -->

  <!-- child Two -->
  <!-- <ChildTwo
    :names="['kshittiz', 'ram', 'shyam']"
    :employee="{ company: 'Kshittiz', employeeType: 'manageer' }"
  /> -->

  <!-- binding multiple properties using object -->
  <ChildThree v-bind="employee" />
</template>

<style scoped></style>
