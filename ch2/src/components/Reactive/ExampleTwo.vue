<script setup>
// understanding deep reactivity
import { reactive } from 'vue';
const state = reactive({
  id: 1,
  profile: {
    name: 'Harry',
    address: 'kalanki',
  },
  subjects: ['science', 'math', 'english'],
});

// changing value of reactive
setTimeout(() => {
  console.log(state); // print proxy(object)
  state.id += 1;
  console.log(state.id);
  // changing the value of profile name
  state.profile.name = 'Ram';
  console.log(state.profile); // Proxy(object)
  console.log(state.profile.name);

  state.subjects.push = 'History';
  console.log(state.subjects); // proxy(Array)
}, 3000);
</script>
<template>
  <div>
    <h4>id: {{ state.id }}</h4>
    <h4>name: {{ state.profile.name }}</h4>
    <h4>address: {{ state.profile.address }}</h4>
    <h4>subject1: {{ state.subjects[0] }}</h4>
    <h4>Subject2: {{ state.subjects[1] }}</h4>
    <h4>Subject3: {{ state.subjects[2] }}</h4>
  </div>
</template>

<style scoped></style>
