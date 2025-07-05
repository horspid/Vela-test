<script setup></script>

<template>
  <form class="search-form">
    <input
      type="search"
      id="search"
      class="search-form__input"
      placeholder="Поиск товаров..."
    />
    <label for="search" class="search-form__label">Найти</label>
  </form>
</template>

<style scoped lang="scss">
.search-form {
  position: relative;
  display: flex;
  align-items: center;

  &__input {
    font-family: "Maza", sans-serif;
    -webkit-appearance: none;
    outline: 0;
    border: 1px solid rgba($color-blue, $alpha: 0.2);
    border-radius: 0.5rem;
    padding-right: 5.5rem;
    padding-left: 1rem;
    height: 3rem;
    width: 654px;
  }

  &__label {
    border-radius: 0.25rem;
    color: $color-gray;
    background-color: $color-blue;
    right: 0.25rem;
    display: inline-flex;
    align-items: center;
    padding: 0 20px;
    height: 2.5rem;
    position: absolute;
  }
}
</style>
