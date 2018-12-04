

<template>
  <ul>
    <li v-for="user in users" :key="user.id">{{user.name}}</li>
  </ul>
</template>

<script>
import axios from "axios";
export default {
  /*
  method from vue & nuxt that allows you to resolve any async data
  */
  async asyncData() {
    const response = await axios.get(
      "https://jsonplaceholder.typicode.com/users"
    );
    return ({ users } = response.data);
  }
};
</script>

<style>
</style>

