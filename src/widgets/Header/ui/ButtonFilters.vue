<script setup>
import { defineEmits } from 'vue';
const emit = defineEmits(['open-popup']);
</script>

<template>
  <button class="btn-filters" @click="emit('open-popup')">
    <svg
      width="41"
      height="16"
      viewBox="0 0 41 16"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <rect width="38" height="2" rx="1" fill="white" />
      <rect y="14" width="38" height="2" rx="1" fill="white" />
      <rect y="7" width="24" height="2" rx="1" fill="white" />
    </svg>
  </button>
</template>

<style scoped lang="scss">
.btn-filters {
  cursor: pointer;
  background-color: $color-blue;
  padding: 0 1.875rem;
  height: 3rem;
  outline: none;
  border-radius: 0.5rem;
  border: none;
}
</style>
