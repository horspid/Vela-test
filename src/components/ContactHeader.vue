<script setup lang="js">
import Header from "./Header.vue";
</script>

<template>
  <div class="contact-header">
    <Container>
      <div class="contact-header__content">
        <div class="contact-geo">
          <div class="contact-geo__item">
            <p>Сайлент-Хилл</p>
          </div>
          <div class="contact-geo__item"></div>
        </div>
        <div class="contact-hours"></div>
        <div class="contact-links"></div>
      </div>
    </Container>
  </div>
</template>

<style scoped lang="scss">
.contact-header {
  &__content {
    display: flex;
    justify-content: space-between;
  }
}

.contact-geo {
  display: flex;

  &__item {
    display: flex;
    align-items: center;
    gap: 6px;
  }
}
</style>
