<script setup lang="js">
const emit = defineEmits(["click"]);
const props = defineProps({
  name: String,
  Icon: Object,
  items: {
    type: Array,
    default: () => []
  },
  isOpen: Boolean
});
</script>

<template>
  <button
    class="mobile-popup-filter-btn"
    :class="{ 'mobile-popup-filter-btn--active': isOpen }"
    @click="emit('click')"
    type="button"
  >
    <component :is="Icon" v-if="Icon" />
    <span>{{ name }}</span>
  </button>
</template>

<style scoped lang="scss">
.mobile-popup-filter-btn {
  font-family: "Maza", sans-serif;
  border-radius: 0.375rem;
  width: max-content;

  background-color: $color-gray;
  padding: 0 1rem;
  height: 3rem;
  color: $color-black;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.625rem;
  cursor: pointer;
  span {
    font-size: 16px;
  }

  svg * {
    fill: $color-blue;
    opacity: 0.5;
  }

  &:hover {
    color: $color-blue;

    svg * {
      opacity: 1;
      transition: opacity 0.4s;
    }
  }
}
</style>
