<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const isOpen = ref({});
const windowWidth = ref(window.innerWidth);

const toggleMenu = (index) => {
  if (windowWidth.value <= 890) {
    isOpen.value[index] = !isOpen.value[index];
  }
};

const updateWindowWidth = () => {
  windowWidth.value = window.innerWidth;
};

onMounted(() => {
  window.addEventListener("resize", updateWindowWidth);
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", updateWindowWidth);
});

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};

const linksItem = [
  "Преимущества",
  "Продукт",
  "Галерея",
  "Партнёры",
  "Отзывы",
  "Заявка",
];
const linksMission = [
  "Повествование",
  "Роадмеп",
  "Релизы",
  "Календарь",
  "Сториук",
  "Художка",
];
const linksResources = [
  "Для инвесторов",
  "Вайтлист",
  "Прайслист",
  "Презентация",
  "Файлы",
];
const linksAbout = [
  "История компании",
  "О основателе",
  "Наша команда",
  "Вакансии",
];

const menuSections = [
  { title: "Link", links: linksItem },
  { title: "Миссия", links: linksMission },
  { title: "Ресурсы", links: linksResources },
  { title: "О нас", links: linksAbout },
];

const linksSocial = [
  { iconSrc: "/img/vk.png", socialSrc: "https://vk.com" },
  {
    iconSrc: "/img/telegram.png",
    socialSrc: "https://web.telegram.org",
  },
  { iconSrc: "/img/youtube.png", socialSrc: "https://www.youtube.com" },
  { iconSrc: "/img/yandex-zen.png", socialSrc: "https://dzen.ru/top" },
];
</script>

<template>
  <div class="footer">
    <div class="wrapper">
      <div class="footer-container">
        <div class="footer-nav flex">
          <div class="footer-menu flex">
            <div
              class="footer-menu__list"
              v-for="(section, index) in menuSections"
              :key="index"
            >
              <p class="footer-menu__title" @click="toggleMenu(index)">
                {{ section.title }}
                <img
                  src="@/assets/img/dropArrow.png"
                  v-if="!isOpen[index] && windowWidth <= 890"
                  class="arrow"
                />
              </p>
              <ul
                :style="{
                  maxHeight:
                    windowWidth > 890 ? 'none' : isOpen[index] ? '300px' : '0',
                  overflow: windowWidth > 890 ? 'visible' : 'hidden',
                  transition:
                    windowWidth > 890 ? 'none' : 'max-height 0.3s ease-in-out',
                }"
              >
                <li
                  v-for="(link, i) in section.links"
                  :key="i"
                  class="footer-menu__item"
                >
                  <a class="footer-menu__link" to="/">{{ link }}</a>
                </li>
              </ul>
            </div>
          </div>
          <div class="footer-nav__contacts">
            <p class="footer-nav__addres">
              г. Москва, ул Пушкина, д. Колотушкина 37,<br />
              каб. 142, дверь справа
            </p>
            <a class="footer-nav__phone" href="tel:+79991234567"
              >+7 (999) 123-45-67</a
            >
            <a class="footer-nav__email" href="mailto:example@example.com"
              >example@example.com</a
            >
            <div class="footer-nav__social flex">
              <a
                v-for="link in linksSocial"
                :key="link.socialSrc"
                :href="link.socialSrc"
                target="_blank"
                rel="noopener noreferrer"
                class="footer-nav__social-link"
              >
                <img :src="link.iconSrc" alt="Иконка" />
              </a>
            </div>
          </div>
        </div>
        <div class="footer-bottom flex">
          <img
            class="footer-bottom__logo"
            src="@/assets/img/logo.png"
            alt="Логотип"
          />
          <p class="footer-bottom__company">ООО «Пример компании», 2020–2023</p>
          <div class="footer-bottom__block-link">
            <a href="/" class="block-link__conf">Политика конфиденциальности</a>
            <a href="/" class="block-link__conf">Публичная оферта</a>
          </div>
          <button class="footer-bottom__button" @click="scrollToTop">
            Вернуться наверх
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer-container {
  padding: 20px 0;
  .footer-nav {
    justify-content: space-between;

    .footer-menu {
      gap: 90px;

      .footer-menu__title {
        margin-bottom: 30px;
        cursor: pointer;
        display: flex;
        color: #fff;
        align-items: center;
        justify-content: space-between;
        font-size: 18px;
        transition: 0.3s;
      }

      .footer-menu__title:hover {
        color: #707a8f;
      }

      .arrow {
        transition: transform 0.3s ease-in-out;
      }

      .arrow.rotate {
        transform: rotate(180deg);
      }

      .footer-menu__item {
        margin-bottom: 16px;
      }

      .footer-menu__link {
        font-size: 16px;
        color: #e2e4e9;
        cursor: pointer;
        transition: 0.3s ease-in-out;
      }

      .footer-menu__link:hover {
        color: #707a8f;
        transition: 0.3s ease-in-out;
        text-decoration: underline;
      }
    }

    .footer-nav__phone,
    .footer-nav__email {
      display: block;
      text-decoration: none;
    }

    .footer-nav__addres,
    .footer-nav__phone,
    .footer-nav__email {
      margin-bottom: 24px;
      line-height: 24px;
      color: #fff;
    }

    .footer-nav__social {
      align-items: center;
      .footer-nav__social-link {
        width: 32px;
        height: 32px;
        transition: 0.3s ease-in-out;
      }

      .footer-nav__social-link:hover {
        transition: 0.3s ease-in-out;
      }

      .footer-nav__social-link:not(:last-child) {
        margin-right: 15px;
      }
    }
  }

  .footer-bottom {
    margin-top: 100px;
    justify-content: space-between;
    align-items: center;

    .footer-bottom__company,
    .block-link__conf {
      color: #707a8f;
    }

    .block-link__conf {
      text-decoration: none;
    }

    .block-link__conf:not(:last-child) {
      margin-right: 30px;
    }

    .footer-bottom__button {
      width: 200px;
      height: 48px;
      padding-right: 40px;
      position: relative;
      border: 1px solid #fff;
      border-radius: 8px;
      background: transparent;
      color: #fff;
      cursor: pointer;
      transition: 0.3s ease-in-out;
    }

    .footer-bottom__button:after {
      content: "";
      position: absolute;
      bottom: 15px;
      right: 29px;
      width: 14px;
      height: 14px;
      background-image: url(/src/assets/img/top.png);
      background-repeat: no-repeat;
      background-position: center;
      background-size: contain;
    }

    .footer-bottom__button:hover {
      background: #464646ff;
      transition: 0.3s ease-in-out;
    }
  }
}

@media (max-width: 1200px) {
  .footer-nav {
    flex-direction: column;
  }

  .footer-menu {
    margin-bottom: 100px;
    justify-content: space-around;
  }

  .footer-nav__contacts {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .footer-bottom {
    flex-direction: column;
  }

  .footer-bottom__block-link {
    display: flex;
    flex-direction: column;
  }

  .footer-bottom__company,
  .block-link__conf {
    margin-bottom: 20px;
  }
}

@media (max-width: 890px) {
  .footer-menu__list ul {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease-in-out;
  }

  .footer-menu {
    flex-direction: column;
  }

  .footer-nav .footer-menu {
    gap: 0;
  }

  .footer-bottom {
    display: block;
    padding-left: 10px;
  }

  .footer-bottom__logo {
    margin-left: -7px;
    margin-bottom: 5px;
  }
}

@media (max-width: 480px) {
  .footer-bottom__button {
    width: 100% !important;
  }

  .footer-bottom__button:after {
    right: 30% !important;
  }
}
</style>