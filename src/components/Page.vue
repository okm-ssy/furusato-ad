<script setup lang="ts">
import Pane from './Pane.vue'
</script>

<template>
  <div class="flex flex-row space-x-1 m-1">
    <Pane class="w-64" :on-hover="() => console.log(1)" />
    <Pane class="w-64" :on-hover="() => console.log(2)" />
    <Pane class="w-64" :on-hover="() => console.log(3)" />
  </div>
</template>

<style scoped>
</style>
