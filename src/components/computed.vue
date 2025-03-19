<script setup>
import { ref, computed } from "vue";

let npm = 0;

const newTodo = ref("");
const hideCompleted = ref(false);
const todos = ref([
  { npm: npm++, text: "budi", keterangan: true },
  { npm: npm++, text: "susi", keterangan: true },
  { npm: npm++, text: "agus", keterangan: false },
  { npm: npm++, text: "dewi", keterangan: false },
  { npm: npm++, text: "dian", keterangan: false },
]);

const filteredTodos = computed(() => {
  return hideCompleted.value
    ? todos.value.filter((t) => !t.keterangan)
    : todos.value;
});

function addTodo() {
  todos.value.push({ npm: npm++, text: newTodo.value, keterangan: false });
  newTodo.value = "";
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" required placeholder="masukkan data" />
    <button>Tambahkan</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.npm">
      <input type="checkbox" v-model="todo.keterangan" />
      <span :class="{ keterangan: todo.keterangan }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? "tamppilkan" : "sembunyikan" }}
  </button>
</template>

<style>
.keterangan {
  text-decoration: line-through;
}
</style>
