<script setup lang="js">
import { defineEmits } from 'vue';
const emit = defineEmits(['open-popup']);
</script>

<template>
  <button class="user-func__btn" @click="emit('open-popup')">
    <svg
      width="16"
      height="16"
      viewBox="0 0 16 16"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M8 3.33333V12.6667"
        stroke="#4888FF"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M3.33337 8H12.6667"
        stroke="#4888FF"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <p>Собрать компьютер</p>
  </button>
</template>

<style scoped lang="scss">

.user-func {
  &__btn {
    cursor: pointer;
    font-family: "Maza", sans-serif;
    width: 176px;
    border-radius: 0.375rem;
    height: 2.625rem;
    color: $color-blue;
    display: flex;
    gap: 7px;
    align-items: center;
    justify-content: center;
    background-color: $color-gray;
    border: none;

    &:hover {
      color: $color-gray;
      background-color: $color-blue;

      svg * {
        stroke: $color-gray;
      }
    }
  }
}
</style>
