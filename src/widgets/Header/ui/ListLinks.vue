<script setup lang="js">
import HeaderLink from '../../../shared/HeaderLink.vue';
import FireIcon from '../../../assets/fire.svg?component';
import LightningIcon from '../../../assets/lightning.svg?component';
import ScrollIcon from '../../../assets/scroll.svg?component';
import ChestIcon from '../../../assets/chest_small.svg?component';
import OrcIcon from '../../../assets/orc.svg?component';
</script>

<template>
  <div class="header-links">
    <HeaderLink name="Акции" :Icon="FireIcon" />
    <HeaderLink name="Горячее предложение" :Icon="LightningIcon" />
    <HeaderLink name="Подарочные наборы" :Icon="ChestIcon" />
    <HeaderLink name="События" :Icon="ScrollIcon" />
    <HeaderLink name="Наши бренды" :Icon="OrcIcon" />
  </div>
</template>

<style scoped lang="scss">
.header-links {
  max-width: 901px;
  width: 100%;
  display: flex;
  justify-content: space-between;
}
</style>
