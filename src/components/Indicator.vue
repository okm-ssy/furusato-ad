<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  value: number
}>();

const width = computed(() => Math.min(props.value,100));
</script>

<template>
  <div
    class="h-4 bg-orange-500"
    :style="{ width: `${width}%` }">
  </div>
</template>

<style scoped>
</style>
