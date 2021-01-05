<template>
  <div class="column is-half">
    <div v-for="(todo, idx) in todos" :key="idx">
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

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: ["todos"],
  methods: {
    toggleComplete(idx: number) {
      this.todos[idx].isCompleted = !this.todos[idx].isCompleted;
    }
  }
});
</script>

<style></style>
