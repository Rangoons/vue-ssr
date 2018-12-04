

<template>
  <pre>
  {{user}}
</pre>
</template>

<script>
import axios from "axios";
export default {
  /*
  method from vue & nuxt that allows you to resolve any async data
  */
  async asyncData({ params, error }) {
    const { data } = await axios.get(
      `https://jsonplaceholder.typicode.com/users/${params.id}`
    );
    return { user: data };
  }
};
</script>

<style>
</style>

