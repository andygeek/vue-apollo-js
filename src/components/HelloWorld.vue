<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div v-for="course in getCourses" :key="course.id">
      {{ course.title }} -
      {{ course.teacher }}
    </div>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  apollo:{
    getCourses: gql`
      query {
        getCourses {
          _id
          title
          teacher
        }
      }
    `
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
