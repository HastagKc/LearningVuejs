<script setup>
// ref in object
import { ref } from 'vue';
const obj = ref({ count: 0 });
// setTimeout(() => {
//   console.log(obj); // RefImp
//   console.log(obj.value); // proxy
//   console.log(obj.value.count); // actual value
//   obj.value.count++;
// }, 3000);

const obj2 = { count: ref(0) };
setTimeout(() => {
  console.log('Obj: ', obj2); // object
  console.log('Obj: ', obj2.count); // RefImp
  console.log('Obj: ', obj2.count.value); // actual value
  obj2.count.value++;
}, 3000);

const obj3 = { count: ref(0) };
let { count } = obj3;
setTimeout(() => {
  console.log('obj3: ', obj3); // object
  console.log('obj3: ', obj3.count); // RefImp
  console.log('obj3: ', obj3.count.value); // actual value
  count++;
}, 3000);
</script>

<template>
  <div>
    <!-- <h1>Count: {{ obj.count }}</h1> -->
    <!-- <h1>Count: {{ obj2.count }}</h1> -->
    <!-- <h1>Count: {{ obj2.count.value + 5 }}</h1>
    <h1>Count: {{ obj2.count + 5 }}</h1>  it won't work-->
    <!-- Count: [object Object]5 -->

    <!-- destructuring -->
    <h2>count: {{ count + 10 }}</h2>
  </div>
</template>

<style scoped></style>
