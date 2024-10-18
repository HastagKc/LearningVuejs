<script setup>
import { computed, reactive } from "vue";
const arrayOfObj = reactive([
  { name: "Ravi", salary: 10000 },
  { name: "Neha", salary: 15000 },
  { name: "Sanjay", salary: 20000 },
  { name: "Priya", salary: 25000 },
  { name: "Vikram", salary: 35000 },
]);

// Computed property to filter based on salary
const filteringSalary = computed(() => {
  return arrayOfObj.filter((person) => person.salary >= 20000);
});
</script>
<template>
  <!-- it is not recommended to use v-if and v-for in same element due to implicit precdence  -->
  <div>
    <!-- we can not do this way, first v-if run then v-for run so it will not find salary -->
    <!-- <ul
      v-for="({ name, salary }, index) in arrayOfObj"
      :key="index"
      v-if="salary >= 20000"
    >
      <li>
        <strong>Name:</strong>{{ name }} <br />
        <strong>Salary: </strong>{{ salary }}
      </li>
    </ul> -->

    <!-- solution One -->
    <!-- <ul v-for="({ name, salary }, index) in arrayOfObj" :key="index">
      <li v-if="salary > 20000">
        <strong>Name:</strong>{{ name }} <br />
        <strong>Salary: </strong>{{ salary }}
      </li>
    </ul> -->

    <!-- Solution filter in computed Properties   -->
    <!-- Solution: Using computed properties to filter -->
    <ul v-for="({ name, salary }, index) in filteringSalary" :key="index">
      <li>
        <strong>Name:</strong> {{ name }} <br />
        <strong>Salary:</strong> {{ salary }}
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
