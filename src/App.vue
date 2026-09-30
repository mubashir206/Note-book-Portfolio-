<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
  <div id="app">
    <RouterView />
  </div>
</template>

<style scoped>
#app {
  min-height: 100vh;
}

@media (max-width: 768px) {
  #app {
    height: 100dvh;
    min-height: 0;
    max-height: 100dvh;
    overflow: hidden;
  }
}
</style>
