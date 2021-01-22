<template>
  <div class="column is-half">
    <div v-for="(todo, idx) in allTodos" :key="idx">
      <div class="todo-item is-flex">
        <input @change="toggleComplete(idx)" type="checkbox" class="toggle" />
        <label
          :class="[
            todo.isCompleted ? 'todo-complete-label' : 'todo-text-label'
          ]"
          class="todo-text-label"
          >{{ todo.title }}
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["todos"],
  data() {
    return {
      allTodos: []
    };
  },
  created() {
    this.allTodos = JSON.parse(localStorage.getItem("todoList")) || [];
  },
  watch: {
    todos() {
      this.allTodos = JSON.parse(localStorage.getItem("todoList")) || [];
    }
  },
  methods: {
    toggleComplete(idx) {
      this.allTodos[idx].isCompleted = !this.allTodos[idx].isCompleted;
    }
  }
};
</script>

<style></style>
