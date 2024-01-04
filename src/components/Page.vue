<script setup lang="ts">
import Pane from './Pane.vue'

const ids = [1, 2, 3]
const onHover = (index: number) => {
  console.log(index)
};
</script>

<template>
  <div class="flex flex-row space-x-1 m-1">
    <Pane
      v-for="id in ids"
      :key="id"
      :id="id.toString()"
      class="w-64"
      :on-hover="() => onHover(id)"
    />
  </div>
</template>

<style scoped>
</style>
