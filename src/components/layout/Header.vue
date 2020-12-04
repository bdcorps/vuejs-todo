<template>
  <header class="header">
    <h1>Todolist Header</h1>
    <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
  </header>
</template>

<script>
export default {
  name: "Header",
  components: {  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style scoped>
.header {
  background-color: #450000;
  color:#FFF000;
}
</style>
