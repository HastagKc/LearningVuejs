<script setup lang="ts">
const imgSrc =
  "https://images.unsplash.com/photo-1492106087820-71f1a00d2b11?q=80&w=1374&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D";
const imgDes = "Girl having Purple hair style";
</script>
<template>
  <!-- attribute binding -->
  <!-- for attribute binding we use v-bind directive and it shorthand is : (colon) -->
  <!-- 
    In Vue, attribute binding allows you to dynamically set HTML attributes 
    using data from your component. Instead of hardcoding attribute values, you can bind 
    them to JavaScript expressions, 
    making your components more flexible and responsive to changes in data.
    -->

  <!-- v-bind use for html attribute, class and id -->
  <div class="imageContainer">
    <div class="image">
      <img :src="imgSrc" :alt="imgDes" />
      <p>{{ imgDes }}</p>
    </div>
  </div>
</template>

<style scoped>
.imageContainer {
  width: 200px;
  height: 200px;
}

.image {
  width: 100%;
  height: 100%;
  border: 2px solid #000;
  padding: 10px;
}

.image img {
  width: 100%;
  height: 70%;
  object-fit: cover;
}
</style>
