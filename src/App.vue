<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
  <RouterView />
</template>

<style>
body {
  margin: 0;
  padding: 0;
  background-color: #f4f7fb; /* Light background for desktop */
}
#app {
  width: 100%;
  min-height: 100vh;
  background-color: transparent;
  overflow-x: hidden;
}
</style>