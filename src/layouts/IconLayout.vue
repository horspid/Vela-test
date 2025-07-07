<template>
  <div class="icon-wrapper">
    <slot></slot>
  </div>
</template>

<style lang="scss">
.icon-wrapper {
  cursor: pointer;
  border-radius: 0.25rem;
  background-color: $color-gray;
  height: 3rem;
  width: 3rem;
  justify-content: center;
  display: flex;
  align-items: center;

  @media (width <= 80rem) {
    width: 2.5rem;
    height: 2.5rem;
  }
}
</style>
