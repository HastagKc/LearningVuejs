<template>
  <div>
    <h2>User Authentication Example</h2>
    <p v-if="user.isLoggedIn" key="welcome">Welcome back, {{ user.name }}!</p>
    <p v-else key="loginPrompt">Please log in to continue.</p>
    <button v-if="!user.isLoggedIn" @click="login">Log In</button>
    <button v-else @click="logout">Log Out</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const user = ref({
  isLoggedIn: false,
  name: 'Kshittiz Chaudhary',
});

const login = () => {
  user.value.isLoggedIn = true;
};

const logout = () => {
  user.value.isLoggedIn = false;
};
</script>

<style scoped>
h2 {
  font-weight: bold;
}

button {
  padding: 10px;
  margin-top: 10px;
}
</style>
