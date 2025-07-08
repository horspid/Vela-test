<script setup>
import { defineEmits, defineProps } from "vue";
const emit = defineEmits(["open-popup"]);

const props = defineProps({
  isOpen: {
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <button
    class="btn-filters"
    :class="{ 'btn-filters--active': props.isOpen }"
    @click="emit('open-popup')"
  >
    <template v-if="props.isOpen">
      <svg
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M19 5L5 19"
          stroke="#343A3F"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
        <path
          d="M5 5L19 19"
          stroke="#343A3F"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </template>
    <template v-else>
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
    </template>
  </button>
</template>

<style scoped lang="scss">
.btn-filters {
  cursor: pointer;
  background-color: $color-blue;
  width: 101px;
  height: 3rem;
  outline: none;
  border-radius: 0.5rem;
  border: none;

  &--active {
    background-color: #e8e8e8;
  }

  @media (width <= 80rem) {
    width: 40px;
    height: 40px;
    padding: 0;

    & {
      border-radius: 0.25rem;
    }

    svg {
      width: 27.5px;
      height: 15px;
    }
  }
}
</style>
