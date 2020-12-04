<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>{{ todo.id }}</p>
    <p>{{ todo.title }}</p>
    <p>{{ todo.completed }}</p>
    <input type="checkbox" @change="markComplete">
    <button @click="$emit('del-todo', todo.id)" class="del">
Delete
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods:{
      markComplete(){
          this.todo.completed =!this.todo.completed
      }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del{
    background-color:#ff0000;
    padding: 20px;
    border: none;
}
</style>