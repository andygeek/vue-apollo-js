<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div v-for="prem in chartTypes" :key="prem._id">
      <h1>{{ prem.name }}</h1>
    </div>
    <button @click="me">Click me</button>
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
  chartTypes: gql`query {
	  chartTypes{
      _id
      name
    }
  }`
  },
  methods:{
    me: function(){
      //console.log(this.Page.users);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
