<script setup>
import { ref } from "vue";

const awesome = ref(true);

function toggle() {
  awesome.value = !awesome.value;
}
</script>

<template>
  <button @click="toggle">toggle</button>
  <h1 v-if="awesome">ini benar</h1>
  <h1 v-else>ini salah</h1>
  <h1>{{ awesome }}</h1>
</template>
