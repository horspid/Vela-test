<script setup>
defineProps({
  name: String,
  Icon: {
    type: Object,
  },
});
</script>

<template>
  <a href="#" class="header__link">
    <component :is="Icon" />
    <p>{{ name }}</p>
  </a>
</template>
<style scoped lang="scss">
.header__link {
  border-radius: 0.375rem;
  width: max-content;
  background-color: $color-gray;
  padding: 0 1rem;
  height: 2.625rem;
  color: $color-black;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.625rem;
  cursor: pointer;

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
