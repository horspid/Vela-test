<template>
  <div class="icon-wrapper icon-wrapper--outlined">
    <slot></slot>
  </div>
</template>

<style lang="scss">
.icon-wrapper--outlined {
  border: 1px solid #d3d3d3;
  background-color: unset;

  svg * {
    fill: #343a3f;
  }

  &:hover {
    svg * {
      fill: $color-blue;
    }
  }
}
</style>
