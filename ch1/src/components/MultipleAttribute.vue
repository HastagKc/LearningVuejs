<script setup lang="ts">
/* 

Multiple Attribute binding in vue:- 
To bind multiple attributes to an element in Vue,
you can use the v-bind directive with an object. This allows you to set multiple
attributes at once by defining them as key-value pairs within the object. Each key in
the object corresponds to the html attribute name, and the value is the data you want to bind
to that attribute. 

*/
// key name should be html attribute
const imageObjAtt = {
    src:
        "https://images.unsplash.com/photo-1492106087820-71f1a00d2b11?q=80&w=1374&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    alt: "Girl having Purple hair style",
};
</script>
<template>
    <div class="imageContainer">
        <div class="image">
            <img v-bind="imageObjAtt" />
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
