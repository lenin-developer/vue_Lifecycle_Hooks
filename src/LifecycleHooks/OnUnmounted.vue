<script setup lang="ts">
import { onUnmounted, onMounted, ref, type Ref } from 'vue';

const container: Ref<HTMLDivElement | null> = ref(null);
const html: Ref<string> = ref('');

let interval;

const setElement = (element: HTMLDivElement) => {
  if (element) {
    html.value += '<span>hola</span>';
  }
};

onMounted(() => {
  interval = setInterval(() => setElement(container.value), 3000);
});

onUnmounted(() => {
  alert('se desmonta el componente');
  clearInterval(interval);
});
</script>

<template>
  <div ref="container" v-html="html"></div>
</template>

<style scoped></style>
