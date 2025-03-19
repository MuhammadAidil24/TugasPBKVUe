<script setup>
import { ref, watch } from "vue";

const todoId = ref(1);
const todoData = ref(null);

async function fetchData() {
  todoData.value = null;
  todoData.value = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  );
  todoData.value = await res.json();
}

fetchData();

watch(todoId, fetchData);
</script>

<template>
  <p>no : {{ todoId }}</p>
  <button @click="todoId++" :disabled="!todoData">data selanjutnya</button>
  <p v-if="!todoData">loading...</p>
  <pre v-else>{{ todoData }}</pre>
</template>
