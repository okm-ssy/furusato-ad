<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  price: number
}>();

const displayText = computed(() => {
  let value = props.price;
  let result = '';
  while (value > 1000) {
    result = `,${Math.floor(value % 1000).toString().padStart(3, '0')}${result}`;
    value /= 1000;
  }
  return `￥${Math.floor(value)}${result}`
})
</script>

<template>
  <div class="price">
    {{ displayText }}
  </div>
</template>

<style scoped>
.price {
  color: black;
  font-size: x-large;
  font-weight: bold;
  text-align: center;
}
</style>
