<script setup lang="ts">
import { ref, watch } from 'vue';
import Indicator from './Indicator.vue';
import Price from './Price.vue';
import DetailButton from './DetailButton.vue';

const props = defineProps<{
  onHover: Function
}>();

const value = ref(0);
setInterval(() => {
  value.value += 1;
}, 30);

const hoverTime = ref(0);
watch(hoverTime, (nextValue) => {
  if (nextValue > 30) {
    props.onHover();
  }
})
</script>

<template>
  <div class="flex flex-col items-center bg-white">
    <Indicator class="w-full self-start" :value="value"></Indicator>
    <img src="../assets/aaa.png" />
    <div class="m-4"></div>
    <Price :price="11000"></Price>
    <div class="m-2"></div>
    <DetailButton
      class="w-1/2"
      text="詳細はこちら"
      href="https://example.com"
    ></DetailButton>
    <div class="m-2"></div>
  </div>
</template>

<style scoped>
</style>
