<script setup lang="ts">
import { onMounted } from 'vue';
defineProps<{
  name: string;
}>();

onMounted(() => {
  alert(`se monto el componente ${name}`);
});
</script>

<template>
  <p>se monto el componente: {{ name }}</p>
</template>

<style scoped></style>
