<template>
  <div class="column is-half">
    <div class="todo-input">
      <form @submit.prevent="createTodo">
        <input
          class="input"
          v-model="todo.title"
          type="text"
          placeholder="What needs to be done?"
        />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      todo: {
        title: "",
        isCompleted: false
      }
    };
  },
  methods: {
    createTodo() {
      this.todos.push(this.todo);
      localStorage.setItem("todoList", JSON.stringify(this.todos));
      this.todos = JSON.parse(localStorage.getItem("todoList"));
      this.$emit("addedTodo", this.todos);
      this.todo = {
        title: "",
        isCompleted: false
      };
    }
  }
};
</script>

<style></style>
