<script setup lang="js">

defineProps({
  links: {
    type: Array,
    required: true,
  },
  popupItemsFilters: {
    type: Array,
    required: false,
    default: () => []
  }
});

import { defineEmits } from 'vue';
import Geolocation from './Geolocation.vue';
import SocialsButtons from './SocialsButtons.vue';
import ButtonComputer from './ButtonComputer.vue';
import ListLinks from './ListLinks.vue';
import MobilePopupFilterButton from './MobilePopupFilterButton.vue'
const emit = defineEmits(['open-popup']);

import FilterSmallIcon from '../../../assets/filterSmall.svg?component';

import { ref } from 'vue';
import Popup from '@/widgets/Popup/index.vue';

const catalog =  { name: 'Каталог', icon: FilterSmallIcon, items: [] };

const isFilterPopupOpen = ref(false);

const changeFilterPopup = () => { isFilterPopupOpen.value = !isFilterPopupOpen.value; };
const closeFilterPopup = () => { isFilterPopupOpen.value = false; };
</script>

<template>
  <Popup
    v-if="isFilterPopupOpen"
    @close="closeFilterPopup"
    :popupItems="popupItemsFilters"
    :isMobile="true"
  />
  <div class="mobile-popup-filter-backdrop" @click.self="$emit('close')">
    <div class="mobile-popup-filter">
      <div class="mobile-popup__contact">
        <div class="mobile-popup__address">
          <Geolocation />
          <div class="contact-hours">
            <svg
              width="16"
              height="16"
              viewBox="0 0 16 16"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <g opacity="0.3">
                <path
                  d="M7.5 2C4.46721 2 2 4.46721 2 7.5C2 10.5328 4.46721 13 7.5 13C10.5328 13 13 10.5328 13 7.5C13 4.46721 10.5328 2 7.5 2ZM10.1157 10.3449C10.0732 10.3876 10.0228 10.4215 9.96714 10.4446C9.91153 10.4677 9.8519 10.4796 9.79167 10.4796C9.73144 10.4796 9.6718 10.4677 9.61619 10.4446C9.56058 10.4215 9.51009 10.3876 9.46762 10.3449L7.17596 8.05321C7.13331 8.01072 7.09949 7.96021 7.07645 7.9046C7.0534 7.84899 7.04158 7.78937 7.04167 7.72917V4.75C7.04167 4.62844 7.08996 4.51186 7.17591 4.42591C7.26186 4.33996 7.37844 4.29167 7.5 4.29167C7.62156 4.29167 7.73814 4.33996 7.82409 4.42591C7.91004 4.51186 7.95833 4.62844 7.95833 4.75V7.53942L10.1157 9.69679C10.1583 9.73932 10.1921 9.78983 10.2152 9.84543C10.2382 9.90104 10.2501 9.96064 10.2501 10.0208C10.2501 10.081 10.2382 10.1406 10.2152 10.1962C10.1921 10.2518 10.1583 10.3023 10.1157 10.3449Z"
                  fill="#343A3F"
                />
              </g>
            </svg>
            <p>Ежедневно</p>
            <p>9:00 — 21:00</p>
          </div>
        </div>
        <SocialsButtons />
      </div>
      <MobilePopupFilterButton
        :name="catalog.name"
        :Icon="catalog.icon"
        :items="catalog.items"
        class="mobile-popup__filter"
        :is-open="isFilterPopupOpen"
        @click="changeFilterPopup"
      />
      <ListLinks class="mobile-popup__mobile" />
      <div class="popup-filter" v-for="link in links" :key="link.title">
        <h3 class="popup-filter__title">{{ link.title }}</h3>
        <div
          class="filter-item"
          v-for="filter in link.items"
          :key="filter.name"
        >
          <div class="filter-item__info">
            <p>{{ filter.name }}</p>
            <p class="filter-item__count">{{ filter.count }}</p>
          </div>
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
            class="filter-item__arrow"
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
      <ButtonComputer class="mobile-popup__computer" />
      <ul class="contact-links">
        <li><a href="">Доставка</a></li>
        <li><a href="">Оплата</a></li>
        <li><a href="">Контакты</a></li>
      </ul>
    </div>
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
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  flex-direction: column;
}
.mobile-popup-filter {
  background: #fff;
  margin-top: 156px;
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

.mobile-popup-filter-btn {
  width: 100%;
  display: flex;
  align-items: center;
  gap: 0.75rem;
  background: $color-gray;
  border: none;
  border-radius: 0.5rem;
  padding: 1rem;
  font-size: 1.125rem;
  color: $color-black;
  cursor: pointer;
  transition: background 0.2s;

  &--active {
    background: $color-blue;
    color: #fff;
  }
}
</style>
