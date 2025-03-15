<script setup>
import { ref } from "vue";

const count = ref(0);

function increment() {
  count.value++;
}
</script>

<template>
  <button type="button" v-on:click="increment">count is {{ count }}</button>
</template>
