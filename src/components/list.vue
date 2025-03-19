<script setup>
import { ref } from "vue";

let npm = 0;

const newtodo = ref("");
const todos = ref([
  { npm: npm++, text: "budi" },
  { mpm: npm++, text: "susi" },
  { npm: npm++, text: "agus" },
  { npm: npm++, text: "dewi" },
  { npm: npm++, text: "dian" },
]);

function addtodo() {
  todos.value.push({
    npm: npm++,
    text: newtodo.value,
  });
  newtodo.value = "";
}

function removetodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}
</script>

<template>
  <form @submit.prevent="addtodo">
    <input v-model="newtodo" required placeholder="masukkan data" />
    <button>Tambah</button>
  </form>
  <ol>
    <li v-for="todo in todos" :key="todo.npm">
      {{ todo.text }}
      <button @click="removetodo(todo)">Hapus</button>
    </li>
  </ol>
</template>
