<script setup lang="js">
import { ref } from 'vue';
import LinkNavMenu from '@/widgets/Header/ui/LinkNavMenu.vue';
const emit = defineEmits(["open-popup"]);

const props = defineProps({
  name: String,
  Icon: {
    type: Object,
    required: false,
  },
  items: {
    type: Array,
    default: () => []
  },

});

const isMenuOpen = ref(false);
const toggleMenu = () => { isMenuOpen.value = !isMenuOpen.value; };
</script>

<template>
  <div class="header-link-wrapper" style="position: relative">
    <a
      href="#"
      class="header__link header__link-mobile"
      @click.prevent="toggleMenu"
    >
      <component :is="Icon" />
      <p>{{ name }}</p>
    </a>
    <LinkNavMenu v-if="isMenuOpen && items && items.length" :items="items" />
  </div>
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

  &-mobile {
    width: inherit;
    height: 3rem;
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
