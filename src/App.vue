<script setup>
import Headercomponent from "./components/headercomponent.vue";
</script>

<template>
  <Headercomponent />
  <RouterView />
</template>

<style>
html {
  scrollbar-gutter: stable; 
}

@supports not (scrollbar-gutter: stable) {
  html { overflow-y: scroll; } 
}

body { margin: 0; }
</style>
