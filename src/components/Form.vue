<template>
  <div>
    <input
      type="text"
      v-model="newTodo"
      placeholder="Write schedule"
      @keyup.enter="addTodo"
      maxlength="100"
    />
    <p>{{ todoLength }} / 100</p>
    <button :disabled="!newTodo.length" @click="addTodo">
      추가
    </button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Form",
  data() {
    return {
      newTodo: "",
    };
  },
  computed: {
    todoLength() {
      return this.newTodo.length;
    },
  },
  methods: {
    addTodo() {
      this.$emit("addTodo", this.newTodo);
      this.newTodo = "";
    },
  },
});
</script>
