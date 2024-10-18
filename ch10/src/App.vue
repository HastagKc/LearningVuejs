<script setup>
import ExampleOne from "./components/defultSlot/ExampleOne.vue";
import ExampleTwo from "./components/defultSlot/ExampleTwo.vue";
import ExampleThree from "./components/defultSlot/ExampleThree.vue";
import BaseLayout from "./components/NameSlot/BaseLayout.vue";

function clickMe() {
  console.log("i am from slot content");
}
</script>

<template>
  <!-- using props -->
  <!-- Pass the name prop as a string by wrapping it in quotes -->
  <!-- <ExampleOne :name="'Kshittiz'" /> -->

  <!-- slot content  -->
  <!-- <ExampleTwo>
    <h2>This slot content comming from parent</h2>
    <button @click="clickMe">Click Me</button>
  </ExampleTwo> -->

  <!-- fallback content -->
  <!-- Not Providing Any Slot content -->
  <!-- <ExampleThree /> -->
  <!-- Providing Slot content -->
  <!-- <ExampleThree>
    <button>Read More</button>
  </ExampleThree> -->

  <!-- Name slots  -->

  <BaseLayout>
    <!-- Named Slot -->
    <!-- using slots -->
    <!-- header -->
    <template v-slot:header>
      <h2>This is Header Slot content Value from parent</h2>
    </template>
    <!-- main -->
    <template v-slot:main>
      <h2>This is Main Slot content Value from parent</h2>
    </template>

    <!-- footer using shorthand-->
    <template #footer>
      <h2>This is footer Slot content value from parent</h2>
    </template>
  </BaseLayout>
</template>

<style scoped></style>
