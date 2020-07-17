<template>
  <div>
    <span @click="toggleTodoStatus(todo)" :class="{completed : todo.completed}">{{ todo.title }}</span>
    <button @click="deleteItem(todo)" style="margin:10px">Delete</button>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  props: ["todo"],
  methods: {
    ...mapActions({
      deleteItem: "deleteTodo"
    }),
    ...mapActions({
      toggleTodoStatus: "toggleTodoStatus"
    })
  }
};
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>