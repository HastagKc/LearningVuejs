<script setup>
import { ref } from 'vue';
// Conditional rendering in Vue.js
const isActive = ref(false);

// Toggle function to switch isActive state
const toggle = () => {
  isActive.value = !isActive.value;
};
</script>

<template>
  <div>
    <!-- This div is conditionally rendered based on isActive -->
    <div :class="['main', isActive ? 'activeClass' : 'inactiveClass']" v-if="isActive">
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi quos dolores similique
        deleniti autem tempore velit libero animi distinctio debitis, id optio at, officiis sed qui
        culpa nobis nulla soluta.
      </p>
    </div>

    <!-- If isActive is false, this div is shown with a dynamically bound class -->
    <div :class="['main', isActive ? 'activeClass' : 'inactiveClass']" v-else>
      <p>Nothing to Show</p>
    </div>

    <!-- Button to toggle the content -->
    <button @click="toggle">{{ isActive ? 'Hide' : 'Show' }}</button>
  </div>
</template>

<style scoped>
.main {
  width: 500px;
  border: 2px solid black;
  padding: 20px;
  font-size: 16px;
  border-radius: 5px;
}

.activeClass {
  background-color: green;
  color: white;
  padding: 10px;
}

.inactiveClass {
  background-color: red;
  color: white;
  padding: 10px;
}

button {
  margin-top: 10px;
  padding: 10px 15px;
  font-size: 16px;
  cursor: pointer;
  border: none;
  border-radius: 5px;
}

button:hover {
  background-color: #007bff;
  color: white;
}
</style>
