<template>
  <form @submit.prevent="createPost">
    <label for="title">title</label>
    <input id="title" type="text" v-model="formData.title" />
    <label for="body">body</label>
    <input id="body" type="text" v-model="formData.body" />
    <label for="userId">userId</label>
    <input id="userId" type="text" v-model="formData.userId" />
    <button>Create Post</button>
  </form>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      formData: {
        title: '',
        body: '',
        userId: '',
      },
    };
  },
  methods: {
    createPost() {
      axios
        .post('https://jsonplaceholder.typicode.com/posts', this.formData)
        .then(res => console.log(res.data))
        .catch(err => console.log(err));
    },
  },
};
</script>

<style scoped>
</style>
