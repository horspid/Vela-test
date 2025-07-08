<script setup lang="js">
import { ref } from "vue";
import PopupFilter from "../Header/ui/PopupFilter.vue";
import Container from '@/layouts/Container.vue'
import HeaderLink from "../../shared/HeaderLink.vue";

defineProps({
  popupItems: {
    type: Array,
    required: true,
  },
  isMobile: {
    type: Boolean,
    required: false,
  }
});

const selectedIndex = ref(null);
const selectCategory = idx => {
  selectedIndex.value = idx === selectedIndex.value ? null : idx;
};
</script>

<template>
  <section class="popup-backdrop">
    <div class="popup">
      <div v-if="isMobile">
        <Container class="popup__heading">
          <div class="popup__arrow" @click="$emit('close')">
            <svg
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
              transform="rotate(180)"
            >
              <path
                d="M9 18L15 12L9 6"
                stroke="#343A3F"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
          <h3 class="popup__title">Каталог</h3>
        </Container>
        <Container>
          <div class="popup-filters">
            <HeaderLink
              class="popup-filters__item popup-filters__item--mobile"
              v-for="(item, idx) in popupItems"
              :key="item.title"
              :name="item.title"
              :Icon="item.Icon"
              :item:="item.items"
              @click="selectCategory(idx)"
            />
          </div>
        </Container>
      </div>
      <div class="popup__inner" v-if="!isMobile">
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
          :isMobile="isMobile"
          :categories="popupItems[selectedIndex].categories"
          class="popup-filters__popup"
        />
      </div>
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

  @media (width <= 80rem) {
    & {
      box-shadow: none;
      border-radius: 0;
      margin-top: 156px;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      width: unset;
    }
  }
}
.popup {
  background: #fff;
  border-radius: 0.5rem;

  &__heading {
    display: flex;
    align-items: center;
    gap: 1.875rem;
  }

  &__inner {
    display: flex;
    position: relative;
    gap: 3rem;
    padding: 1.875rem 6rem 1.875rem 0;

    @media (width <= 80rem) {
      padding: 0;
    }
  }

  &__title {
    font-size: 1.25rem;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
  }
}

.popup-filters {
  max-width: 338px;

  @media (width <= 80rem) {
    max-width: unset;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  &__category {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
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

    &--mobile {
      width: 100%;
      border: 0;
      padding: 0;
    }

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

  &__arrow {
    margin-left: auto;
    flex-shrink: 0; // чтобы не сжималась
    display: block;
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
