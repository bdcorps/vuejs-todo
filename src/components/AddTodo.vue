<template>
  <div class="add-todo">
    <h1>Add Todo</h1>
    <form @submit="addTodo">
      <input
        type="text"
        v-model="title"
        @change="setNewTodoTitle"
        placeholder="Enter title"
      />
      <input type="submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  components: {},
  data() {
    return {
      title: "",
    };
  },
  methods: {
    setNewTodoTitle(e) {
      console.log(e.target.value);
      this.title = e.target.value;
      console.log(this.title);
    },
    addTodo(e) {
      e.preventDefault();
      const todo = { id: 45, title: this.title, completed: false };
      console.log(todo);
      this.$emit("add-todo", todo);
      this.title = '';
    },
  },
};
</script>

<style scoped>
.addtodo {
}
</style>
