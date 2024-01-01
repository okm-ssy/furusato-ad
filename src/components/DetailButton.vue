<script setup lang="ts">
defineProps<{
  text: string,
  href: string
}>();
</script>

<template>
  <a
    class="button"
    :href="href"
    target="_blank"
  >
    {{ text }}
  </a>
</template>

<style scoped>
.button {
  padding: 4px;
  color: white;
  font-weight: bold;
  border-radius: 9999px;
  background-color: #EE6611;
  text-align: center;
}
</style>
