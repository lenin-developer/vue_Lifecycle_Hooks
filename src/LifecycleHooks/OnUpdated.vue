ojo el onUpdated se ejecuta cuando el dom cambio, no cuando el estado cambia es
decir si cambio un estado pero este no altera el dom (el contenido visual) no se
ejecuta, solo si el DOM cambia

<script setup lang="ts">
import { type Ref, ref, onUpdated } from 'vue';
const state: Ref<boolean> = ref(false);

const handleClick = () => {
  state.value = !state.value;
};

onUpdated(() => {
  alert(' se actualizo el DOM; onUpdate');
});
</script>

<template>
  <p>el DOM de este componente cambio {{ state }}</p>
  <button @click="handleClick">cambiar el estado</button>
</template>

<style scoped></style>
