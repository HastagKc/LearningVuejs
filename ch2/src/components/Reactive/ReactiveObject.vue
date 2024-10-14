<script setup>
// What is reactive object

//     Reactive objects in Vue.js are special objects that allow Vue to "reactively"
// track changes to their properties.When you modify a property of a reactive object,
//     Vue detects the change and automatically updates the DOM wherever that property
// is referenced.
// This system is core to Vue’s reactivity, enabling efficient, data - driven UIs.
// In Vue 3, you create reactive objects using the `reactive()` function from the Composition
// API.This function wraps an object in a proxy that Vue uses to track and respond to changes.

// reactive object is used in more complex data like arrays and objects

// creating reactive objects
// import reactive function from vue

import { reactive } from 'vue';
const state = reactive({
  count: 0,
  user: {
    name: 'Kshittiz',
    profile: {
      age: 22,
      city: 'kathmandu',
    },
  },
});

// accessing properties
console.log(state.count);
console.log(state.user.name);
console.log(state.user.profile.age);

// modify properties
state.count += 1;
state.user.name = 'Harry Potter';
console.log(state.count);
console.log(state.user.name);

// Adding new properties (Vue will track them)
state.newProp = 'New Properties is added';
console.log(state.newProp);
</script>
<template>
  <div>
    <h1>This is reactive Object</h1>
  </div>
</template>

<style></style>
