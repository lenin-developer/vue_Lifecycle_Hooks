se ejecuta cuando un elemento reactivo modifica el dom el collback solo se
ejecuta una vez, independientemente de cuantos elementos reactivos se ejecutaron

<script setup lang="ts">
import { ref, onRenderTriggered, reactive } from 'vue';
const num = ref(0);
const num2 = ref(10);

const handleClik = () => {
  num.value++;
};

const handleClik2 = () => {
  num2.value++;
  num.value++;
};

onRenderTriggered((e) => {
  console.log('effect', e.effect);
  console.log('target', e.target);
  console.log('type', e.type);
  console.log('key', e.key);
  console.log('newValue', e.newValue);
  console.log('oldValue', e.oldValue);
  console.log('oldTarget', e.oldTarget);
});
</script>

<template>
  <p>modificando num: {{ num }}</p>
  <button @click="handleClik">clcik</button>
  <p>modificando num: {{ num2 }}</p>
  <button @click="handleClik2">clcik</button>
</template>

<style scoped></style>
