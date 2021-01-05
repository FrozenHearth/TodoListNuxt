<template>
  <div class="container is-flex-direction-column">
    <h1 class="title">
      Todo
    </h1>
    <TodoInput @addedTodo="addedTodo" />
    <TodoLists :todos="todos" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import TodoLists from "~/components/todos/TodoLists.vue";

export default Vue.extend({
  components: { TodoLists },
  data() {
    return {
      todos: Array()
    };
  },
  methods: {
    addedTodo(todos: Array<any>) {
      this.todos = todos;
    }
  }
});
</script>

<style>
body {
  background-color: #f5f5f5;
}
* {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
