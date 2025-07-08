<script setup lang="js">
import Container from "../../../layouts/Container.vue";
import Geolocation from "./Geolocation.vue";
import LanguageSwitcher from './LanguageSwitcher.vue'
</script>

<template>
  <div class="contact-header">
    <Container>
      <div class="contact-header__content">
        <LanguageSwitcher class="contact-lang" />
        <div class="contact-geo">
          <Geolocation />
          <div class="contact-geo__item">
            <svg
              width="16"
              height="16"
              viewBox="0 0 16 16"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M10.3364 1.34649H5.6638C5.44518 1.34586 5.2286 1.38845 5.0265 1.47182C4.8244 1.55519 4.64078 1.67769 4.48619 1.83228C4.33161 1.98687 4.20911 2.17049 4.12574 2.37259C4.04237 2.57469 3.99977 2.79127 4.0004 3.00989V12.9903C4.0004 13.9127 4.75649 14.6537 5.6638 14.6537H10.3364C10.5551 14.6543 10.7716 14.6117 10.9737 14.5283C11.1758 14.445 11.3595 14.3225 11.514 14.1679C11.6686 14.0133 11.7911 13.8297 11.8745 13.6276C11.9579 13.4255 12.0005 13.2089 11.9998 12.9903V3.00989C12.0005 2.79127 11.9579 2.57469 11.8745 2.37259C11.7911 2.17049 11.6686 1.98687 11.514 1.83228C11.3595 1.67769 11.1758 1.55519 10.9737 1.47182C10.7716 1.38845 10.5551 1.34586 10.3364 1.34649ZM8.00768 13.58C7.58427 13.58 7.25159 13.2474 7.25159 12.8239C7.25159 12.4005 7.58427 12.0679 8.00768 12.0679C8.43109 12.0679 8.76377 12.4005 8.76377 12.8239C8.76377 13.2474 8.43109 13.58 8.00768 13.58ZM11.2437 11.2664H4.75649V3.5694H11.2437V11.2664Z"
                fill="#343A3F"
                fill-opacity="0.5"
              />
            </svg>
            <p>+7 555 555-37-50</p>
          </div>
        </div>
        <div class="contact-hours">
          <p>Ежедневно</p>
          <p>9:00 — 21:00</p>
        </div>
        <ul class="contact-links">
          <li><a href="">Доставка</a></li>
          <li><a href="">Оплата</a></li>
          <li><a href="">Контакты</a></li>
        </ul>
      </div>
    </Container>
  </div>
</template>

<style scoped lang="scss">
.contact-header {
  display: block;
  padding: 7px 0;
  background-color: $color-gray;

  @media (width <= 80rem) {
    margin-bottom: 0.625rem;
  }

  &__content {
    display: flex;
    align-items: center;
    justify-content: space-between;

    color: $color-black;
    font-size: 14px;
  }
}

.contact-geo {
  display: flex;
  gap: 12px;

  &__item {
    display: flex;
    align-items: center;
    gap: 5px;
  }

  @media (width <= 80rem) {
    &__location {
      display: none;
    }
  }
}

.contact-hours {
  display: flex;
  align-items: center;
  gap: 12px;

  @media (width < 80rem) {
    display: none;
  }
}

.contact-links {
  display: flex;
  align-items: center;
  gap: 16px;
  list-style-type: none;

  a {
    text-decoration: none;
    color: $color-black;

    &:hover {
      color: $color-blue;
    }
  }

  @media (width <= 80rem) {
    display: none;
  }
}

.contact-lang {
  display: none;

  @media (width <= 80rem) {
    display: flex;
  }
}
</style>
