<script setup>
import { ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";

const modules = [Navigation, Pagination];

const isModalOpen = ref(false);
const modalContent = ref({
  avatar: "",
  name: "",
  job: "",
  text: "",
});

const openModal = (avatar, name, job, text) => {
  modalContent.value = { avatar, name, job, text };
  isModalOpen.value = true;
};

const closeModal = () => {
  isModalOpen.value = false;
};
</script>

<template>
  <div class="reviews padding">
    <div class="wrapper">
      <div class="compnent-block-title flex">
        <h2 class="component-title">Отзывы</h2>
      </div>
      <div class="slider">
        <Swiper
          :modules="modules"
          :pagination="{
            el: '.swiper-pagination',
            type: 'fraction',
          }"
          :slides-per-view="3"
          :space-between="24"
          :navigation="{
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev',
          }"
          :breakpoints="{
            1200: { slidesPerView: 3 },
            900: { slidesPerView: 2 },
            375: { slidesPerView: 1 },
          }"
          class="swiper-container"
        >
          <SwiperSlide>
            <div class="slide">
              <div class="slide-user flex">
                <div class="slide-user__img">
                  <img src="@/assets/img/slider-avatar-1.png" alt="Фото" />
                </div>
                <div class="slide-user__name">
                  <p class="slide-user__title">Федот Сергеев</p>
                  <p class="slide-user__job">Дизайнер</p>
                </div>
              </div>
              <p class="slide-user__text">
                Я использовал этот софт для фрилансера и был впечатлен его
                функциональностью и простотой использования. Программа помогла
                мне организовать свою работу и улучшить эффективность выполнения
                задач. Особенно мне нравится, что софт предоставляет возмож...
              </p>
              <button
                class="slide-user__button"
                @click="
                  openModal(
                    '/img/modal-avatar-1.png',
                    'Федот Сергеев',
                    'Дизайнер',
                    'Я использовал этот софт для фрилансера и был впечатлен его функциональностью и простотой использования. Программа помогла мне организовать свою работу и улучшить эффективность выполнения задач. Особенно мне нравится, что софт предоставляет возможность создавать и отправлять запросы на выполнение работ, а также следить за своим временем и расходованием ресурсов.Я использовал этот софт для фрилансера и был впечатлен его функциональностью и простотой использования. Программа помогла мне организовать свою работу и улучшить эффективность выполнения задач. Особенно мне нравится, что софт предоставляет возможность создавать и отправлять запросы на выполнение работ, а также следить за своим временем и расходованием ресурсов.'
                  )
                "
              >
                Показать ещё
              </button>
            </div>
          </SwiperSlide>
          <SwiperSlide>
            <div class="slide">
              <div class="slide-user flex">
                <div class="slide-user__img">
                  <img src="@/assets/img/slider-avatar-2.png" alt="Фото" />
                </div>
                <div class="slide-user__name">
                  <p class="slide-user__title">Болексей Арисов</p>
                  <p class="slide-user__job">Разработчик</p>
                </div>
              </div>
              <p class="slide-user__text">
                Я использовал этот софт для фрилансера и был впечатлен его
                функциональностью и простотой использования. Программа помогла
                мне организовать свою работу и улучшить эффективность выполнения
                задач. Особенно мне нравится, что софт предоставляет возмож...
              </p>
              <button
                class="slide-user__button"
                @click="
                  openModal(
                    '/img/modal-avatar-2.png',
                    'Болексей Арисов',
                    'Разработчик',
                    'В целом, я считаю, что этот софт для фрилансера - это хороший выбор для тех, кто стремится улучшить свою рабочую эффективность и успешно координировать свои проекты. Он упрощает процессы и облегчает работу, что делает его очень полезным инструментом для фрилансеров.'
                  )
                "
              >
                Показать ещё
              </button>
            </div>
          </SwiperSlide>
          <SwiperSlide>
            <div class="slide">
              <div class="slide-user flex">
                <div class="slide-user__img">
                  <img src="@/assets/img/slider-avatar-3.png" alt="Фото" />
                </div>
                <div class="slide-user__name">
                  <p class="slide-user__title">Маман Рамаев</p>
                  <p class="slide-user__job">Техлид в РЖД</p>
                </div>
              </div>
              <p class="slide-user__text">
                лагодаря этому софту я смог значительно улучшить свою
                эффективность и организацию, что, в свою очередь, позволило мне
                зарабатывать больше денег и удовлетворять потребности моих
                клиентов. Хорошие функции, такие как автоматизация платежей и
                ...
              </p>
              <button
                class="slide-user__button"
                @click="
                  openModal(
                    '/img/modal-avatar-3.png',
                    'Маман Рамаев',
                    'Техлид в РЖД',
                    'Благодаря этому софту я смог значительно улучшить свою эффективность и организацию, что, в свою очередь, позволило мне зарабатывать больше денег и удовлетворять потребности моих клиентов. Хорошие функции, такие как автоматизация платежей и напоминания о задачах, делают его незаменимым инструментом для фрилансеров.'
                  )
                "
              >
                Показать ещё
              </button>
            </div>
          </SwiperSlide>
          <SwiperSlide>
            <div class="slide">
              <div class="slide-user flex">
                <div class="slide-user__img">
                  <img src="@/assets/img/slider-avatar-1.png" alt="Фото" />
                </div>
                <div class="slide-user__name">
                  <p class="slide-user__title">Федот Сергеев</p>
                  <p class="slide-user__job">Дизайнер</p>
                </div>
              </div>
              <p class="slide-user__text">
                Я использовал этот софт для фрилансера и был впечатлен его
                функциональностью и простотой использования. Программа помогла
                мне организовать свою работу и улучшить эффективность выполнения
                задач. Особенно мне нравится, что софт предоставляет возмож...
              </p>
              <button
                class="slide-user__button"
                @click="
                  openModal(
                    '/img/modal-avatar-1.png',
                    'Федот Сергеев',
                    'Дизайнер',
                    'Я использовал этот софт для фрилансера и был впечатлен его функциональностью и простотой использования. Программа помогла мне организовать свою работу и улучшить эффективность выполнения задач. Особенно мне нравится, что софт предоставляет возможность создавать и отправлять запросы на выполнение работ, а также следить за своим временем и расходованием ресурсов.Я использовал этот софт для фрилансера и был впечатлен его функциональностью и простотой использования. Программа помогла мне организовать свою работу и улучшить эффективность выполнения задач. Особенно мне нравится, что софт предоставляет возможность создавать и отправлять запросы на выполнение работ, а также следить за своим временем и расходованием ресурсов.'
                  )
                "
              >
                Показать ещё
              </button>
            </div>
          </SwiperSlide>
        </Swiper>
        <div class="custom-navigation">
          <div class="swiper-button-prev"></div>
          <div class="swiper-pagination"></div>
          <div class="swiper-button-next"></div>
        </div>
      </div>
    </div>
    <div v-if="isModalOpen" class="modal">
      <div class="modal-content">
        <span class="close" @click="closeModal"></span>

        <div class="slide">
          <div class="modal-user flex">
            <div class="slide-user__img">
              <img :src="modalContent.avatar" alt="Фото" />
            </div>
            <div class="modal-user__name">
              <p class="modal-user__title">{{ modalContent.name }}</p>
              <p class="modal-user__job">{{ modalContent.job }}</p>
            </div>
          </div>
          <p class="modal-user__text">{{ modalContent.text }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.slider {
  position: relative;
  margin-top: 50px;

  .swiper-container {
    width: 100%;
    overflow: hidden;

    .slide {
      margin: 0 auto;
      max-width: 456px;
      padding: 38px;
      border-radius: 8px;
      border: 1px solid #434956;

      &-user {
        align-items: center;

        &__img {
          width: 56px;
          height: 56px;
          border-radius: 50%;
        }

        &__name {
          margin-left: 16px;

          .slide-user__title {
            font-size: 20px;
            font-weight: 500;
            color: #fff;
          }

          .slide-user__job {
            font-size: 16px;
            font-weight: 400;
            color: #707a8f;
          }
        }
      }
      &-user__text {
        margin-top: 32px;
        font-size: 16px;
        font-weight: 400;
        line-height: 24px;
        color: #e2e4e9;
      }

      &-user__button {
        margin-top: 16px;
        padding: 0;
        font-size: 16px;
        color: #4452fe;
        border: none;
        background-color: transparent;
        cursor: pointer;
      }
    }
  }
  .custom-navigation {
    width: 180px;
    margin: 0 auto;
    padding-top: 72px;
    display: flex;
    justify-content: space-between;
    pointer-events: none;
    z-index: 10;

    .swiper-button-prev,
    .swiper-button-next {
      position: static;
      pointer-events: all;
      width: 48px;
      height: 48px;
      border-radius: 8px;
      border: 1px solid #fff;
      background-color: transparent;
      cursor: pointer;
    }

    .swiper-button-prev,
    .swiper-button-next {
      background-position: center;
      background-repeat: no-repeat;
    }

    .swiper-button-prev {
      background-image: url(../assets/img/button-prev.png);
    }

    .swiper-button-next {
      background-image: url(../assets/img/button-next.png);
    }

    .swiper-pagination {
      font-size: 16px;
      font-weight: bold;
      color: #fff;
      min-width: 40px;
      text-align: center;
    }

    .swiper-wrapper {
      justify-content: center;
    }
  }

  :deep(.swiper-button-next::after),
  :deep(.swiper-button-prev::after) {
    content: "";
    display: none;
  }
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-content {
  max-width: 456px;
  height: auto;
  background: #22252b;
  padding: 40px;
  border-radius: 8px;
  width: 100%;
  position: relative;
}

.close {
  width: 48px;
  height: 48px;
  position: absolute;
  top: 0px;
  right: -65px;
  border-radius: 8px;
  border: 1px solid #fff;
  background-image: url(../assets/img/close.png);
  background-repeat: no-repeat;
  background-position: center;
  cursor: pointer;
}

.modal-user {
  align-items: center;
  background-color: #22252b;
}

.modal-user__name {
  margin-left: 16px;
}

.modal-user__title {
  font-size: 20px;
  font-weight: 500;
  color: #fff;
}

.modal-user__job {
  font-size: 16px;
  font-weight: 400;
  color: #707a8f;
}

.modal-user__text {
  margin-top: 32px;
  font-size: 16px;
  font-weight: 400;
  line-height: 24px;
  color: #e2e4e9;
}
</style>