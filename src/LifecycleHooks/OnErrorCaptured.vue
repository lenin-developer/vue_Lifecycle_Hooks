<script setup lang="ts">
import { onErrorCaptured } from 'vue';
import ErrorComponent from '../components/ErrorComponent.vue';

onErrorCaptured((err, instance, info) => {
  alert('se produjo un error en un componente Hijo');
  console.warn('err', err);
  console.log('instance', instance);
  console.log('info', info);
  return false;
});
</script>

<template>
  <div class="container">
    <ErrorComponent />
    <ErrorComponent />
  </div>
</template>

<style scoped>
.container {
  border: 1px solid red;
  padding: 20px;
}
</style>
