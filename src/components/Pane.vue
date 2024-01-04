<script setup lang="ts">
import { ref } from 'vue';
import Indicator from './Indicator.vue';
import Price from './Price.vue';
import DetailButton from './DetailButton.vue';

const props = defineProps<{
  id: string,
  onHover: Function
}>();

const hoverTimer = ref(0);
const counterInterval = ref(0);
const maxValue = 100;

function specificFunction() {
  // 特定の関数の内容
  props.onHover();
  console.log('called', props.id);
}

function startCounting() {
  counterInterval.value = setInterval(() => {
    hoverTimer.value++;
    if (hoverTimer.value >= maxValue) {
      stopCounting();
      specificFunction();
    }
  }, 10);
}

function stopCounting() {
  hoverTimer.value = 0; // カウントをリセット
  clearInterval(counterInterval.value);
}
</script>

<template>
  <div
    :id="id"
    class="flex flex-col items-center bg-white"
    @mouseenter="startCounting"
    @mouseleave="stopCounting"
  >
    <Indicator class="w-full self-start" :value="hoverTimer" :max-value="maxValue"></Indicator>
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
