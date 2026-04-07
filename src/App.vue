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
  background-color: #eaf1fa; /* Added a light blue background for the out-of-phone area to mimic the design mockup's background */
}
#app {
  max-width: 414px; /* Mobile width */
  margin: 0 auto;
  min-height: 100vh;
  box-shadow: 0 0 20px rgba(0,0,0,0.1);
  background-color: #fff;
  overflow-x: hidden;
}
</style>