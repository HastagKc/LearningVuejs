<script setup></script>
<template>
  <div>
    <!-- Name slot definition -->
    <slot name="header">
      <h2>This is Header Slot Outlet default Value</h2>
    </slot>

    <!-- main  -->
    <slot name="main"></slot>

    <!-- footer -->
    <slot name="footer"></slot>
  </div>
</template>

<style scoped></style>
