<script setup lang="js">

defineProps({
  items: {
    type: Array,
    required: true
  }
});
</script>

<template>
  <section class="link-menu link-menu__mobile">
    <div class="link-menu__item" v-for="item in items" :key="item.name">
      <a href="#" class="link-menu__name">{{ item.name }}</a>
    </div>
  </section>
</template>

<style lang="scss">
.link-menu {
  margin-top: 1.5rem;
  display: flex;
  flex-direction: column;
  padding: 1.5rem 4.375rem 1.5rem 1.5rem;
  gap: 1rem;
  position: absolute;
  top: 100%;
  border-radius: 0.5rem;
  width: max-content;
  background: #fff;
  box-shadow: 0px 0px 10px 0px rgba(157, 157, 157, 35%);
  z-index: 1000;

  &__mobile {
    display: none;
  }
  &__name {
    color: $color-black;
    text-decoration: none;
  }
}
</style>
