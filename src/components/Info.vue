<template>
  <div>
    <span v-if="amountTodo === 0">할일끝!!!</span>
    <span v-else> 할일이 {{ amountTodo }} 개 남았습니다.</span>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Info",
  props: {
    amountTodo: {
      type: Number,
      required: true,
    },
  },
});
</script>
