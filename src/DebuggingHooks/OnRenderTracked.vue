el onRenderTracked se ejecuta cada vez que se renderiza el componente en el Dom
(ya sea por que monto por primera vez o se actualizo) y el callback se ejecuta
el numero de veces de elementos reactivos que se encuentran en el template Nota:
esto no detecta el cambio de un componente hijo o padre

<script setup lang="ts">
import { ref, onRenderTracked, reactive } from 'vue';
import ChildrenComp from '../components/ChildrenComp.vue';

const objRef = reactive({ nombre: 'lenin' });
const cont = ref(0);

const handleRef = () => {
  cont.value++;
};

const handleReactive = () => {
  objRef.nombre += '+';
};

onRenderTracked((e) => {
  console.log('effect', e.effect);
  console.log('target', e.target);
  console.log('key', e.key);
});
</script>

<template>
  <p>dependiencias reactivas {{ cont }}</p>
  <p>dependiencias reactivas {{ objRef.nombre }}</p>
  <button @click="handleRef">a</button>
  <button @click="handleReactive">b</button>
  <ChildrenComp />
</template>

<style scoped></style>
