<script setup lang="js">

import { defineEmits } from 'vue';
const emit = defineEmits(['open-popup']);


const filterСategory = {
    phones: {
        title: 'Смартфоны',
        items: [
            { name: 'Apple iPhone', count: 123 },
            { name: 'Смартфоны', count: 227 },
            { name: 'iPhone 16', count: 120 },
            { name: 'Складные', count: 30 },
            { name: 'realme', count: 120 },
            { name: 'Huawei Mate X6', count: 100 },
            { name: 'Кнопочные', count: 23 },
            { name: 'Домашние', count: 17 },
            { name: 'Samsung', count: 27 },
        ]
    },
    gadgets: {
        title: 'Гаджеты',
        items: [
            { name: 'Смарт-часы', count: 15 },
            { name: 'Смарт-кольца', count: 34 },
            { name: 'Наушники', count: 21 },
            { name: 'Гарнитуры', count: 12 },
            { name: 'Портативное аудио', count: 42 },
            { name: 'Умные гаджеты', count: 46 },
            { name: 'Очки VR', count: 49 },
            { name: 'Для блогеров', count: 32 },
        ]
    }
}

</script>

<template>
    <div class="popup-filter" v-for="item in filterСategory" :key="item.title">
        <h3 class="popup-filter__title">{{ item.title }}</h3>
        <div class="filter-item" v-for="filter in item.items" :key="filter.name">
            <div class="filter-item__info">
                <p>{{ filter.name }}</p>
                <p class="filter-item__count">{{ filter.count }}</p>
            </div>
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="filter-item__arrow">
                <path d="M9 18L15 12L9 6" stroke="#343A3F" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
        </div>
    </div>
</template>

<style scoped lang="scss">
    .popup-filter {
        flex: 1;
        display: flex;
        flex-direction: column;
        gap: 1rem;

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
                transition: opacity .4s;
                stroke: $color-blue;
                stroke-width: 2px;
            }
        }

        &__arrow path{
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
</style>