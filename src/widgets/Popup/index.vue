<script setup>
import { ref } from 'vue';
import PopupFilter from '../Header/ui/PopupFilter.vue';

defineProps({
  items: {
    type: Array,
    required: true
  }
});

const openFilter = ref(false);
const changeFilters = () => { openFilter.value = !openFilter.value; };

</script>

<template>
  <section class="popup-backdrop">
    <div class="popup">
      <div class="popup-filters">
        <div class="popup-filters__item" v-for="item in items" :key="item.title" @click="changeFilters">
          <div class="popup-filters__content">
            <component :is="item.Icon" />
            <p>{{ item.title }}</p>
          </div>
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="popup-filters__arrow">
            <path d="M9 18L15 12L9 6" stroke="#343A3F" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
      </div>
      <PopupFilter />
    </div>
  </section>
</template>

<style scoped lang="scss">
.popup-backdrop {
  position: absolute;
  top: 100%;
  border-radius: 0.5rem;
  width: 892px;
  background: #fff;
  box-shadow: 0px 0px 10px 0px rgba(157, 157, 157, 35%);
  z-index: 1000;
}
.popup {
  display: flex;
  flex: 1 1 1;
  gap: 3rem;
  padding: 1.875rem 6rem 1.875rem 0;
  background: #fff;
  border-radius: 0.5rem;
  position: relative;
}

.popup-filters {
  
  &__content {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  &__item {
    display: flex;
    flex: 1;
    align-items: center;
    justify-content: space-between;
    padding: 0.825rem 0 0.825rem 2rem;
    border-bottom: 1px solid $color-gray;
    cursor: pointer;

    &:last-child {
      border-bottom: none;
    }

    svg * {
      fill: $color-blue;
      opacity: 0.5;
    }

    &:hover {
      background-color: $color-gray;

      .popup-filters__arrow path{
        stroke: $color-blue;
        stroke-width: 2px;
      }
    }
  }

  &__arrow path {
    fill: none;
    opacity: 1;
  }
}
</style>
