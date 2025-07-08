<script setup lang="js">
import DesktopHeader from './ui/DesktopHeader.vue';
import ContactHeader from './ui/ContactHeader.vue';
import MobileHeader from './ui/MobileHeader.vue';

import Phone from '@/assets/phone.svg?component'
import Laptop from '@/assets/laptop.svg?component'
import Tv from '@/assets/tv.svg?component'
import Speaker from '@/assets/speaker.svg?component'
import Fire from '@/assets/fire.svg?component'
import New from '@/assets/new.svg?component'
import Reshot from '@/assets/reshot.svg?component'
import People from '@/assets/people.svg?component'
import Computer from '@/assets/computer.svg?component'

const popupItemsFilters = [
  {
    Icon: Phone,
    title: 'Смартфоны и гаджеты',
    categories: [
      {
        title: 'Смартфоны',
        count: 0,
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
      {
        title: 'Гаджеты',
        count: 0,
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
    ]
  },
  { Icon: Laptop, title: 'Ноутбуки и компьютеры', count: 0,},
  { Icon: Tv, title: 'Телевизоры и цифровое ТВ', count: 0},
  { Icon: Speaker, title: 'Аудиотехника', count: 0},
  { Icon: Fire, title: 'Акции', count: 0},
  { Icon: New, title: 'Новинки', count: 0},
]

const popupItemsComputer = [
  {
    Icon: People,
    title: 'Кому',
    categories: [
      {
        title: 'Кому',
        count: 0,
        items: [
            { name: 'Для мужчин', count: 123, items: [] },
            { name: 'Для женщин', count: 63, items: [] },
            { name: 'Папе', count: 120, items: [] },
            { name: 'Сотрудникам', count: 30, items: [] },
            { name: 'Мужу', count: 120, items: [] },
            { name: 'Корпоративный', count: 100, items: [] },
        ]
      }
    ]
  },
  { Icon: Reshot, title: 'Повод', categories: []},
  { Icon: Computer, title: 'Наполнение', categories: [] },
]
</script>

<template>
  <header>
    <ContactHeader />
    <DesktopHeader
      :itemsFilters="popupItemsFilters"
      :computerFilters="popupItemsComputer"
    />
    <MobileHeader
      :itemsFilters="popupItemsFilters"
      :computerFilters="popupItemsComputer"
    />
  </header>
</template>

<style scoped lang="scss"></style>
