<script setup lang="ts">
import { ref } from "vue";

const title = ref("Hello World");
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
  </div>
</template>