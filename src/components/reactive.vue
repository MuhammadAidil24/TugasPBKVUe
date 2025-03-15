<script setup>
import { ref } from "vue";

const count = ref(0);
const pesan = ref("assamualaikum");
</script>

<template>
  <h1>{{ pesan }}</h1>
  <p>{{ count }}</p>
</template>
