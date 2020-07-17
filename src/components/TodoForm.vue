<template>
  <div>
    <input type="text" v-model="newTodoItem" />
    <button @click="submit">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: ""
    };
  },
  methods: {
    submit() {
      this.$store.dispatch("addNewTodo", this.newTodoItem);
      this.newTodoItem = "";
    }
  }
};
</script>