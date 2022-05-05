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
export default {
  data() {
    return {
      posts: [],
      errMsg: "",
    };
  },
  methods: {
    getPosts() {
      fetch("https://jsonplaceholder.typicode.com/posts")
        .then((res) => {
          if (!res.ok) {
            throw Error(res.statusText);
          }
          return res.json();
        })
        .then((data) => (this.posts = data))
        .catch(() => (this.errMsg = "error fetching data"));
    },
  },
};
</script>

<style scoped>
</style>