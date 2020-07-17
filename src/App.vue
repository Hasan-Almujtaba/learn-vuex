<template>
  <div id="app">
    <h1>Todos</h1>
    <h1>Completed {{ completedNumber }}</h1>
    <h1>Pending {{ pendingNumber }}</h1>
    <todo-list></todo-list>
    <todo-form></todo-form>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import TodoList from "./components/TodoList.vue";
import TodoForm from "./components/TodoForm.vue";

export default {
  name: "App",
  components: {
    TodoList,
    TodoForm
  },
  computed: {
    ...mapGetters({
      completedNumber: "completedTodos"
    }),
    ...mapGetters({
      pendingNumber: "pendingTodos"
    })
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
