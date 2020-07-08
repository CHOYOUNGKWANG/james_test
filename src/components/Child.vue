<template>
  <div>Child : {{ name }}</div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component({
  props: ["name"],
})
export default class Child extends Vue {}
</script>
