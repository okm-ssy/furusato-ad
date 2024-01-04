<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  value: number,
  maxValue: number
}>();

const width = computed(() => 100 * Math.min(props.value ?? 0, props.maxValue) / props.maxValue);
</script>

<template>
  <div
    class="h-4 bg-orange-500"
    :style="{ width: `${width}%` }">
  </div>
</template>

<style scoped>
</style>
