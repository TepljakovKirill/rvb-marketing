<script setup>
import { ref } from "vue";

const scrollTo = (id) => {
  const element = document.querySelector(id);
  if (element) {
    window.scrollTo({
      top: element.offsetTop - 70,
      behavior: "smooth",
    });
  }
};

const linksSocial = [
  { iconSrc: "/img/vk.png", socialSrc: "https://vk.com" },
  {
    iconSrc: "/img/telegram.png",
    socialSrc: "https://web.telegram.org",
  },
  { iconSrc: "/img/youtube.png", socialSrc: "https://www.youtube.com" },
  { iconSrc: "/img/yandex-zen.png", socialSrc: "https://dzen.ru/top" },
];

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  document.body.style.overflow = isMenuOpen.value ? "hidden" : "";
};
</script>

<template>
  <div class="header">
    <div class="wrapper">
      <div class="header-container flex">
        <img class="header-logo" src="@/assets/img/logo.png" alt="Логотип" />
        <nav
          :class="[
            'header-menu',
            'flex',
            { 'header-menu__active': isMenuOpen },
          ]"
        >
          <ul class="header-menu__list flex">
            <li class="header-menu__item">
              <router-link
                class="header-menu__link"
                to="#advantages"
                @click="scrollTo('#advantages')"
                >Преимущества</router-link
              >
            </li>
            <li class="header-menu__item">
              <router-link
                class="header-menu__link"
                to="#product"
                @click="scrollTo('#product')"
                >Продукт</router-link
              >
            </li>
            <li class="header-menu__item">
              <router-link
                class="header-menu__link"
                to="#gallery"
                @click="scrollTo('#gallery')"
                >Галерея</router-link
              >
            </li>
            <li class="header-menu__item">
              <router-link
                class="header-menu__link"
                to="#partners"
                @click="scrollTo('#partners')"
                >Партнеры</router-link
              >
            </li>
            <li class="header-menu__item">
              <router-link
                class="header-menu__link"
                to="#reviews"
                @click="scrollTo('#reviews')"
                >Отзывы</router-link
              >
            </li>
          </ul>
          <div v-if="isMenuOpen" class="header-social-link">
            <ul class="flex">
              <li v-for="(link, index) in linksSocial" :key="index">
                <a class="social-link flex" :to="link.socialSrc">
                  <img :src="link.iconSrc" alt="Иконка" />
                </a>
              </li>
            </ul>
          </div>
          <button v-if="isMenuOpen" class="modal-menu__button">
            Попробовать бесплатно
          </button>
        </nav>
        <div class="button-block flex">
          <button class="header-button">Войти</button>

          <button class="burger-button" @click="toggleMenu">
            <span class="burger-line"></span>
            <span class="burger-line"></span>
            <span class="burger-line"></span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.header {
  width: 100%;
  position: fixed;
  background-color: #16181d;
  z-index: 1000;

  .header-container {
    height: 80px;
    justify-content: space-between;
    align-items: center;

    .header-menu li:not(:last-child) {
      margin-right: 30px;
    }

    .header-menu__link {
      padding-bottom: 20px;
      color: #fff;
      border-bottom: 2px solid transparent;
      cursor: pointer;
      transition: 0.3s ease-in-out;
      text-decoration: none;
    }

    .header-menu__link:hover {
      border-bottom: 2px solid #4452fe;
      transition: 0.3s ease-in-out;
    }

    .header-button {
      width: 95px;
      height: 48px;
      border-radius: 8px;
      border: 1px solid #fff;
      background: transparent;
      color: #fff;
      cursor: pointer;
      transition: 0.3s ease-in-out;
    }

    .header-button:hover {
      background-color: #464646ff;
      transition: 0.3s ease-in-out;
    }

    .burger-button {
      display: none;
      flex-direction: column;
      justify-content: space-between;
      height: 24px;
      background: none;
      border: none;
      cursor: pointer;
      z-index: 1100;

      .burger-line {
        width: 24px;
        height: 2px;
        background-color: #fff;
        transition: 0.3s ease-in-out;
      }
    }

    .header-social-link {
      padding-left: 20px;
    }

    .modal-menu__button {
      width: 94%;
      height: 48px;
      align-self: center;
      background-color: #4452fe;
      border-radius: 8px;
      color: #fff;
      font-size: 16px;
      border: none;
    }

    .button-block {
      align-items: center;

      .burger-button {
        margin-left: 33px;
      }
    }
  }
}

@media (max-width: 890px) {
  .burger-button {
    display: flex !important;
  }

  .header-menu__list {
    flex-direction: column;
    padding-left: 20px;
  }

  .header-menu {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100vh;
    padding-bottom: 80px;
    position: fixed;
    padding-top: 40px;
    top: 65px;
    left: -100%;
    width: 100%;
    height: 100vh;
    background: #16181d;
    flex-direction: column;
    transition: left 0.3s ease-in-out;
  }

  .header-menu__active {
    left: 0;
  }

  .header-menu__item {
    padding: 12px 0;
  }
}

@media (max-width: 380px) {
  .header-logo {
    width: 143px;
    height: 40px;
  }

  .header .header-container .header-button {
    width: 80px;
    height: 34px;
  }
}
</style>