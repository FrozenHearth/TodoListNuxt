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

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  data() {
    return {
      todos: Array(),
      todo: {
        title: "",
        isCompleted: false
      }
    };
  },
  methods: {
    createTodo() {
      this.todos.push(this.todo);
      this.$emit("addedTodo", this.todos);
      this.todo = {
        title: "",
        isCompleted: false
      };
    }
  }
});
</script>

<style></style>
