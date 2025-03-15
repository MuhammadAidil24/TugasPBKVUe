<script setup>
import { ref } from "vue";

const judul = ref("saya");
</script>

<template>
  <h1 :class="judul">nama saya aidil</h1>
</template>

<style scoped>
.saya {
  color: aqua;
  font-size: 50px;
}
</style>
