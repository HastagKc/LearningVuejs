<script setup>
import DefaultSlotScoped from "./components/defaultSlotScoped/DefaultSlotScoped.vue";
import NameSlotScoped from "./components/namedSlotScoped/NameSlotScoped.vue";
</script>

<template>
  <!-- slot content parent can access child properties using slotProps -->

  <!-- <DefaultSlotScoped v-slot="slotProps">
    <p>{{ slotProps }}</p>
    <h2>Name: {{ slotProps.name }}</h2>
    <h3>Job: {{ slotProps.job }}</h3>
    <h4>Age: {{ slotProps.age }}</h4>
  </DefaultSlotScoped> -->

  <!-- NameSlotScoped -->
  <NameSlotScoped>
    <template v-slot:header="{ nm, age }">
      <!-- <div>{{ headerProps }}</div> -->
      <h2>{{ nm }}</h2>
      <h3>{{ age }}</h3>
    </template>

    <!-- main -->
    <template v-slot:main="mainProps">
      <h4>{{ mainProps.des }}</h4>
    </template>
  </NameSlotScoped>
</template>

<style scoped></style>
