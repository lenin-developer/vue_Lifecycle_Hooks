<script setup lang="ts">
import {type Ref, ref} from 'vue'
import HelloWorld from './components/HelloWorld.vue';
import FooterComp from './components/FooterComp.vue';
import OnMounted from './LifecycleHooks/OnMounted.vue';
import OnUpdated from './LifecycleHooks/OnUpdated.vue';
import OnUnmounted from './LifecycleHooks/OnUnmounted.vue';
import OnErrorCaptured from './LifecycleHooks/OnErrorCaptured.vue';
import OnRenderTracked from './DebuggingHooks/OnRenderTracked.vue';
import OnRenderTriggered from './DebuggingHooks/OnRenderTriggered.vue';

const onMountedRef: Ref<boolean> = ref(false)
const onUpdatedRef: Ref<boolean> = ref(true)
const onUnmountedRef: Ref<boolean> = ref(false)




</script>

<template>
  <HelloWorld msg="Vite + Vue" />
  <h1>vue - Lifecycle Hooks</h1>

  <section class='title' >
  <h3>onMounted</h3>
  <input type='checkbox' v-model='onMountedRef' >montar/desmontar </input>
  </section>
  <onMounted v-if='onMountedRef' name="OnMounted" />
  <hr />

  <section class='title' >
  <h3>OnUpdated</h3>
  <input type='checkbox' v-model='onUpdatedRef' >montar/desmontar </input>
  </section>
  <OnUpdated v-if='onUpdatedRef' />
  <hr />

  <section class='title' >
  <h3>OnUnmounted</h3>
  <input type='checkbox' v-model='onUnmountedRef' >montar/desmontar </input>
  </section>
  <OnUnmounted v-if='onUnmountedRef' />
  <hr />

  <section class='title' >
  <h3>OnErrorCaptured</h3>
  </section>
  <OnErrorCaptured />
  <hr />


  <section class='title' >
  <h3>OnRenderTracked</h3>
  </section>
  <OnRenderTracked />
  <hr />

  <section class='title' >
  <h3>OnRenderTriggered</h3>
  </section>
  <OnRenderTriggered />
  <hr />

  <FooterComp />
</template>

<style scoped>

.title {
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>
