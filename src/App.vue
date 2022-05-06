<template>
  <h1>vue-http</h1>
  <create-post />
  <post-list />
</template>

<script>
import CreatePost from "./components/CreatePost.vue";
import PostList from "./components/PostList.vue";
export default {
  name: "App",
  components: { PostList, CreatePost },
};
</script>

<style>
</style>
