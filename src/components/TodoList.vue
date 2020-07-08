<template>
  <ul>
    <li
      v-for="todo in todos"
      :key="todo.id"
      @click="$emit('selectTodo', todo)"
      :class="{ strikeout: todo.completed }"
    >
      {{ todo.text }}
    </li>
  </ul>
</template>

<script lang="ts">
import Vue from "vue";
// import { ITodo } from "../models/ITodo";

export default Vue.extend({
  name: "TodoList",
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
});
</script>
<style>
.strikeout {
  text-decoration: line-through;
  color: crimson;
}

.order {
  color: blue;
}
</style>
