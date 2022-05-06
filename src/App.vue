<template>
  <button @click="counter"> counter clicked
    {{ count }} times
  </button>
</template>

<script>
import CounterMixin from './mixins/counter';
export default {
  name: "App",
  mixins: [CounterMixin]
};
</script>

<style>
</style>
