<script setup lang="ts">
import { ref } from "vue";
import graphVue from "./components/graph.vue";

const title = ref("Hello World");
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <graphVue />
  </div>
</template>