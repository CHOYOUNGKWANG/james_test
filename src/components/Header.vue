<template>
  <div>
    <h1>{{ header }}</h1>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Header",
  props: {
    header: {
      type: String,
      required: true,
    },
  },
});
</script>
