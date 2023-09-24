<script setup lang="ts">
import useStore from "../store/index";

const { api } = useStore();
</script>

<template>
    <div>
        <p v-for="data in api.data">{{ data.cost }}</p>
    </div>
</template>