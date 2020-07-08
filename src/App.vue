<template>
  <div>
    <header-component :header="header" />
    <form-component @addTodo="addTodo" />
    <info-component :amount-todo="todos.length" />
    <todo-list-component :todos="reverseTodos" @selectTodo="complete" />
  </div>
</template>

<script>
import Vue from "vue";
import HeaderComponent from "./components/Header.vue";
import FormComponent from "./components/Form.vue";
import TodoListComponent from "./components/TodoList.vue";
import InfoComponent from "./components/Info.vue";
// import { ITodo } from "./models/ITodo";

export default Vue.extend({
  name: "app",
  components: {
    HeaderComponent,
    FormComponent,
    TodoListComponent,
    InfoComponent,
  },
  data: function () {
    return {
      header: "Todo List",
      todos: [
        { id: 1, text: "sleep", completed: false },
        { id: 2, text: "play", completed: true },
        { id: 3, text: "eat", completed: false },
      ],
    };
  },
  computed: {
    reverseTodos() {
      return this.todos.slice(0).reverse();
    },
  },
  methods: {
    addTodo(newTodo) {
      if (newTodo.length > 0) {
        this.todos.push({
          id: this.todos.length + 1,
          text: newTodo,
          completed: false,
        });
      }
    },
    complete(todo) {
      todo.completed = !todo.completed;
    },
  },
});
</script>
