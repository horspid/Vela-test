<script setup lang="js">

const emit = defineEmits(['open-popup']);
</script>

<template>
  <div class="mobile-popup-filter-backdrop" @click.self="$emit('close')">
    <div class="mobile-popup-filter">Дароу</div>
  </div>
</template>

<style scoped lang="scss">
.contact-links {
  margin-top: 2.5rem;
  margin-bottom: 1.5rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  list-style-type: none;

  a {
    display: block;
    width: 100%;
    padding-bottom: 0.625rem;
    border-bottom: 1px solid #e8e8e8;
    text-decoration: none;
    color: $color-black;

    &:hover {
      color: $color-blue;
    }
  }
}
.mobile-popup__mobile {
  margin-top: 0.625rem;
  gap: 0.625rem;
  flex-direction: column;
}
.mobile-popup {
  &__computer {
    margin-top: 1.5rem;
    width: inherit;
    height: 3rem;
  }

  &__contact {
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
.mobile-popup-filter-backdrop {
  margin-top: 156px;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  flex-direction: column;
  z-index: 10000;
}
.mobile-popup-filter {
  background: #fff;
  flex: 1 1 auto;
  overflow-y: auto;
  padding: 2rem 1rem 1rem 1rem;
  display: flex;
  flex-direction: column;
  position: relative;
}
.mobile-popup-filter__close {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: none;
  border: none;
  font-size: 2rem;
  color: #888;
  cursor: pointer;
  z-index: 10;
}
.popup-filter {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 100%;

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
.contact-hours {
  margin-top: 0.5rem;
  display: flex;
  align-items: center;
  gap: 0.625rem;
}
</style>
