<script setup lang="js">

defineProps({
  categories: {
    type: Array,
    required: true,
  },
});

import { defineEmits } from 'vue';
const emit = defineEmits(['open-popup']);
</script>

<template>
  <div
    class="popup-filter"
    v-for="category in categories"
    :key="category.title"
  >
    <h3 class="popup-filter__title">{{ category.title }}</h3>
    <div
      class="filter-item"
      v-for="filter in category.items"
      :key="filter.name"
    >
      <div class="filter-item__info">
        <p>{{ filter.name }}</p>
        <p class="filter-item__count">{{ filter.count }}</p>
      </div>
      <svg
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        class="filter-item__arrow"
      >
        <path
          d="M9 18L15 12L9 6"
          stroke="#343A3F"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </div>
  </div>
</template>

<style scoped lang="scss">
.popup-filter {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 200px;

  &__title {
    font-size: 1.875rem;
    margin-bottom: 1.5rem;
  }
}

.filter-item {
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: space-between;

  &:hover {
    color: $color-blue;

    .filter-item__count {
      color: $color-blue;
      opacity: 1;
    }

    .filter-item__arrow path {
      opacity: 1;
      transition: opacity 0.4s;
      stroke: $color-blue;
      stroke-width: 2px;
    }
  }

  &__arrow path {
    opacity: 0;
  }

  &__count {
    color: $color-black;
    opacity: 0.5;
  }

  &__info {
    display: flex;
    gap: 0.5rem;
    align-items: center;
  }
}
</style>
