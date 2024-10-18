<script setup></script>
<template>
  <!-- fallback content-->
  <div>
    <h2>Fallback Content</h2>
    <p>
      Fallback Content work as default value when no slot content provided from parent.
      Fallback Content is written child Component, inside slot outlet
    </p>
    <slot>
      <!-- this is a fallback content, if content provide from parent it will get replaced  -->
      <button>See More</button>
    </slot>
  </div>
</template>

<style scoped></style>
