<script setup lang="js">
import HeaderLink from '../../../shared/HeaderLink.vue';
import FireIcon from '../../../assets/fire.svg?component';
import LightningIcon from '../../../assets/lightning.svg?component';
import ScrollIcon from '../../../assets/scroll.svg?component';
import ChestIcon from '../../../assets/chest_small.svg?component';
import OrcIcon from '../../../assets/orc.svg?component';

const linkItems = [
  { name: 'Акции', icon: FireIcon, items: [] },
  { name: 'Горячее предложение', icon: LightningIcon, items: [] },
  { name: 'Подарочные наборы', icon: ChestIcon, items: [] },
  {
    name: 'События',
    icon: ScrollIcon,
    items: [
      {name: 'ИгроМИР'},
      {name: 'Мероприятия'},
      {name: 'Мастер-классы'}
    ]
  },
  { name: 'Наши бренды', icon: OrcIcon, items: [] },
]
</script>

<template>
  <div class="header-links">
    <HeaderLink
      v-for="item in linkItems"
      :key="item.name"
      :name="item.name"
      :Icon="item.icon"
      :items="item.items"
    />
  </div>
</template>

<style scoped lang="scss">
.header-links {
  overflow: hidden;
  max-width: 901px;
  width: 100%;
  display: flex;
  justify-content: space-between;

  @media (width <=80rem) {
    & {
      max-width: unset;
    }
  }
}
</style>
