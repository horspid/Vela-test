<script setup lang="js">
import Container from '../../layouts/Container.vue';
</script>

<template>
  <section class="hero">
    <Container>
      <div class="hero__info">
        <h1 class="hero__title">
          Отправляйся в приключения с нашими эпическими лут-корзинами и
          наборами!
        </h1>
        <p class="hero__text">
          Развивай свои навыки, следуя мудрым стратегиям мастеров, и поднимайся
          на новый уровень мастерства! С нашей поддержкой каждое твое действие
          станет частью великого искусства, а победы — результатом точного плана
          и безупречной подготовки!
        </p>
        <button class="hero__btn">В каталог</button>
      </div>
    </Container>
  </section>
</template>

<style scoped lang="scss">
.hero {
  height: calc(100vh - 176px);
  width: 100%;
  background-image: url("../../assets/banner.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: right center;

  font-family: "Tenor", sans-serif;
  color: $color-gray;

  &__info {
    padding-top: 2rem;
  }

  &__title {
    max-width: 730px;
    font-size: 2rem;
    line-height: 2.25rem;
  }

  &__text {
    margin-top: 1.625rem;
    max-width: 580px;
    line-height: 1.5rem;
  }

  &__btn {
    margin-top: 1.625rem;
    color: #672870;
    cursor: pointer;
    font-size: 1rem;
    border-radius: 0.5rem;
    background-color: $color-gray;
    outline: none;
    padding: 1rem 2.25rem;
    border: none;
    font-family: "Maza", sans-serif;
  }
}
</style>
