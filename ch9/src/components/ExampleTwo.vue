<script setup>
// 1. objects
import { reactive } from "vue";
// objects
const myObject = reactive({
  title: "How to do lists in Vue",
  author: "Jane Doe",
  publishedAt: "2016-04-10",
});

// list in object
const people = reactive([
  {
    name: "Kshittiz",
    job: "Vue Developer",
    subject: ["Science", "Math", "English"],
  },
  {
    name: "Anjali",
    job: "Data Scientist",
    subject: ["Statistics", "Machine Learning", "Data Visualization"],
  },
  {
    name: "Rajesh",
    job: "Backend Developer",
    subject: ["Node.js", "Databases", "API Development"],
  },
  {
    name: "Meera",
    job: "Graphic Designer",
    subject: ["Photoshop", "Illustration", "UI/UX Design"],
  },
  {
    name: "Siddharth",
    job: "Project Manager",
    subject: ["Agile Methodologies", "Scrum", "Team Management"],
  },
  {
    name: "Ayesha",
    job: "Content Writer",
    subject: ["Creative Writing", "SEO", "Copywriting"],
  },
]);

//3. object of objects
// Define an object of objects
const books = reactive({
  book1: {
    title: "How to do lists in Vue",
    author: "Jane Doe",
    publishedAt: "2016-04-10",
  },
  book2: {
    title: "Learning Vue 3",
    author: "John Smith",
    publishedAt: "2020-05-15",
  },
  book3: {
    title: "Advanced Vue.js Techniques",
    author: "Alice Johnson",
    publishedAt: "2022-09-01",
  },
});
</script>
<template>
  <div>
    <!--1. simple objects -->
    <!-- 
    <ul>
      <li v-for="(value, index) in myObject" :key="index">{{ value }}</li>
    </ul>
    -->

    <!-- 2. List in object -->
    <!-- <ul>
      <li v-for="(value, index) in people" :key="index">
        <Strong>Name:</Strong>{{ value.name }} <br />
        <Strong>Job:</Strong>{{ value.job }} <br />
        <Strong>Subject:</Strong>

        <ul>
          <li v-for="(value, index) in value.subject" :key="index">
            {{ value }}
          </li>
        </ul>
      </li>
    </ul> -->

    <!--3. object of object -->
    <!-- Loop through the object of objects -->
    <!-- <ul>
      <li v-for="(book, key) in books" :key="key">
        <strong>{{ key }}:</strong>
        <ul>
          <li><strong>Title:</strong> {{ book.title }}</li>
          <li><strong>Author:</strong> {{ book.author }}</li>
          <li><strong>Published At:</strong> {{ book.publishedAt }}</li>
        </ul>
      </li>
    </ul> -->

    <!-- using destructuring techniques -->
    <ul>
      <li v-for="({ title, author, publishedAt }, key) in books" :key="key">
        <strong>{{ key }}:</strong>
        <ul>
          <li><strong>Title:</strong> {{ title }}</li>
          <li><strong>Author:</strong> {{ author }}</li>
          <li><strong>Published At:</strong> {{ publishedAt }}</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
