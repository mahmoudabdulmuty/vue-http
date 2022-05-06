<template>
  <button @click="getPosts">Load Posts</button>
  <ul>
    <li v-if="errMsg">
      {{ errMsg }}
    </li>
    <li v-for="post in posts" :key="post.id">
      <h3>{{ post.id }}. {{ post.title }}</h3>
      <p>
        {{ post.body }}
      </p>
      <hr />
    </li>
  </ul>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      posts: [],
      errMsg: "",
    };
  },
  methods: {
    getPosts() {
      axios
        .get("https://jsonplaceholder.typicode.com/posts")
        .then((res) => (this.posts = res.data))
        .catch((err) =>
          console.log(err.message)((this.errMsg = "err fetching data"))
        );
    },
  },
  created() {
    this.getPosts();
  },
};
</script>

<style scoped>
</style>