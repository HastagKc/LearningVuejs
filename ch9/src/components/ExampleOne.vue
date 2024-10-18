<script setup>
import { ref } from "vue";

// array of string
const names = ref(["harry", "jhon", "jonny", "kshittiz"]);

// array of object
const arrayOfObj = ref([
  { name: "Ravi", salary: 850000 },
  { name: "Neha", salary: 920000 },
  { name: "Sanjay", salary: 1100000 },
  { name: "Priya", salary: 750000 },
  { name: "Vikram", salary: 980000 },
  { name: "Sonal", salary: 1050000 },
  { name: "Kiran", salary: 870000 },
  { name: "Rajesh", salary: 990000 },
  { name: "Aditi", salary: 1150000 },
  { name: "Manoj", salary: 940000 },
]);

// array of arrays
const arrayOfArr = ref([
  ["Java", "Andorid"],
  ["Python", "Ml"],
  ["Dart", "Hybird App Development"],
]);
</script>

<template>
  <div>
    <!-- <h3>List of Student</h3>
    <ul v-for="(name, i) in names" :key="i">
      <li>Student: {{ i + 1 }} = {{ name }}</li>
    </ul> -->

    <!-- list of object  -->
    <!-- <h4 v-for="(obj, index) in arrayOfObj" :key="index">
      Name: {{ obj.name }} - Rs: {{ obj.salary }}
    </h4> -->

    <!-- using destructuring -->
    <!-- <h4 v-for="({ name, salary }, index) in arrayOfObj" :key="index">
      {{ name }} - Rs{{ salary }}
    </h4> -->

    <!-- array of array i.e. 2d array -->
    <!-- this approch give div for each item in an array -->
    <div v-for="(item, outerIndex) in arrayOfArr" :key="outerIndex">
      {{ item }}
      <h2 v-for="(innerItem, innerIndex) in item" :key="innerIndex">
        Index of [{{ outerIndex }} {{ innerIndex }}] {{ innerItem }}
      </h2>
    </div>

    <!-- use template to remove div to create each time when item get iterate -->
    <!-- Rendering a 2D array without additional wrapper elements -->
    <!-- <template v-for="(outerItem, outerIndex) in arrayOfArr" :key="outerIndex">
      <h2>Main Index {{ outerIndex }}</h2>
      <template v-for="(innerItem, innerIndex) in outerItem" :key="innerIndex">
        <p>Index [{{ outerIndex }}, {{ innerIndex }}]: {{ innerItem }}</p>
      </template>
    </template> -->
  </div>
</template>

<style scoped></style>
