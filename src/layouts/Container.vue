<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<style lang="scss">
.container {
  width: 100%;
  max-width: 1440px;
  margin: 0 auto;

  @media (width <= 1440px) {
    width: unset;
    max-width: unset;
    padding: 0 1rem;
  }
}
</style>
