<script setup>
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then((response) => response.json())
  .then((json) => console.log(json));
</script>
<template>
  <div>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Delectus nulla quod
      voluptatem atque deserunt ipsum sequi, debitis cupiditate, pariatur at consequatur
      voluptate minus ab officiis minima, ea labore possimus. Inventore.
    </p>
  </div>
</template>

<style scoped></style>
