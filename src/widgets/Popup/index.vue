<script setup lang="js">
import { ref } from "vue";
import PopupFilter from "../Header/ui/PopupFilter.vue";

defineProps({
  popupItems: {
    type: Array,
    required: true,
  },
});

const selectedIndex = ref(null);
const selectCategory = idx => {
  selectedIndex.value = idx === selectedIndex.value ? null : idx;
};
</script>

<template>
  <section class="popup-backdrop">
    <div class="popup">
      <div class="popup-filters">
        <div
          class="popup-filters__item"
          v-for="(item, idx) in popupItems"
          :key="item.title"
          @click="selectCategory(idx)"
        >
          <div class="popup-filters__category">
            <div class="popup-filters__content">
              <component :is="item.Icon" />
              <p>{{ item.title }}</p>
            </div>
            <svg
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
              class="popup-filters__arrow"
            >
              <path
                d="M9 18L15 12L9 6"
                stroke="#343A3F"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
        </div>
      </div>
      <PopupFilter
        v-if="selectedIndex !== null"
        :categories="popupItems[selectedIndex].categories"
        class="popup-filters__popup"
      />
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
  position: relative;
  gap: 3rem;
  padding: 1.875rem 6rem 1.875rem 0;
  background: #fff;
  border-radius: 0.5rem;
}

.popup-filters {
  max-width: 338px;

  &__category {
    display: flex;
    align-items: center;
  }
  &__content {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  &__item {
    display: flex;
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

      .popup-filters__arrow path {
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

.popup-filters__popup {
  position: absolute;
  top: 0;
  left: 50%;
  min-width: 320px;
  background: #fff;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.15);
  border-radius: 1rem;
  z-index: 10;
  margin-left: 1rem;
  height: 100%;
}
</style>
