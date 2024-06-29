<script setup lang="ts">
import { ref, onRenderTracked, reactive } from 'vue';
const num = ref(0);

const handleClik = () => {
  num.value++;
};

onRenderTracked((e) => {
  console.log('effect children', e.effect);
  console.log('target children', e.target);
  console.log('key children', e.key);
});
</script>

<template>
  <p>modificando num: {{ num }}</p>
  <button @click="handleClik">clcik</button>
</template>

<style scoped></style>
