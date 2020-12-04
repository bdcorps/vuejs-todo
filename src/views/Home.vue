<template>
  <div id="app">
    <Header/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    <AddTodo v-on:add-todo="addTodo"/>
  </div>
</template>

<script>
import axios from "axios"
import Todos from "../components/Todos"
import AddTodo from "../components/AddTodo"
export default {
  name: "Home",
  components: {AddTodo, Todos},
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Pick up groceries",
          completed: true,
        }
      ],
    };
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(e => e.id !== id);
    },
    addTodo(todo){
      this.todos.push(todo)
      console.log(this.todos);
    }
  },
    async created(){
      const res = await axios.get("https://jsonplaceholder.typicode.com/todos?_limit=5");

      this.todos = res.data;
    }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
