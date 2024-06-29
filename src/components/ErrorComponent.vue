<script setup lang="ts">
const generateError = () => {
  soyUnaFuntionQueNoExiste();
};
</script>

<template>
  <div class="container">
    <button @click="generateError">Error</button>
  </div>
</template>

<style scoped>
.container {
  border: 1px solid red;
  padding: 20px;
}
</style>
