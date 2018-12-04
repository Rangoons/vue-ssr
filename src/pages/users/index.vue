

<template>
  <ul>
    <li v-for="user in users" :key="user.id">
      <nuxt-link :to="'/users/' + user.id">{{user.name}}</nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from "axios";
export default {
  /*
  method from vue & nuxt that allows you to resolve any async data
  */
  async asyncData() {
    const { data } = await axios.get(
      "https://jsonplaceholder.typicode.com/users"
    );
    return { users: data };
  }
};
</script>

<style>
</style>

