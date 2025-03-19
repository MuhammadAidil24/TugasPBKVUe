<script setup>
import { ref, onMounted } from "vue";

const kata = ref(null);

onMounted(() => {
  kata.value.textContent = "waalaikumsalam";
});
</script>

<template>
  <p ref="kata">assalamualaikum</p>
</template>
