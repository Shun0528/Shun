<script setup lang="ts">
import { ref } from "vue";
import Cost from "./components/cost.vue";
import useStore from "./store/index";

const { api } = useStore();
const title = ref("Hello World");
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <table class="date">
      <tr>
        <td v-for="data in api.data">{{ data.date }}</td>
      </tr>
    </table>
    <Cost />
  </div>
</template>

<style scoped>
.date {
  border: 1px solid #000;
  margin-bottom: 20px;
}
</style>