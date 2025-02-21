<script setup>
import { ref } from "vue";

const initialImages = [
  "/img/gallery-1.jpg",
  "/img/gallery-2.jpg",
  "/img/gallery-3.jpg",
  "/img/gallery-4.jpg",
  "/img/gallery-5.jpg",
  "/img/gallery-6.jpg",
  "/img/gallery-7.jpg",
];

const moreImages = [
  "/img/gallery-1.jpg",
  "/img/gallery-2.jpg",
  "/img/gallery-3.jpg",
  "/img/gallery-4.jpg",
  "/img/gallery-5.jpg",
  "/img/gallery-6.jpg",
  "/img/gallery-7.jpg",
];

const images = ref([...initialImages]);
const modalImage = ref(null);
const isMoreLoaded = ref(false);

const toggleMore = () => {
  if (isMoreLoaded.value) {
    images.value = [...initialImages];
  } else {
    images.value = [...initialImages, ...moreImages];
  }
  isMoreLoaded.value = !isMoreLoaded.value;
};

const openModal = (image) => {
  modalImage.value = image;
};

const closeModal = () => {
  modalImage.value = null;
};
</script>

<template>
  <div class="gallery padding">
    <div class="wrapper">
      <div class="compnent-block-title flex">
        <h2 class="component-title">Галерея</h2>
        <p class="compnent-about">
          Мы уделяем особое внимание эргономике и стараемся соответствовать
          месту работы
        </p>
      </div>

      <div class="gallery-wrap">
        <div class="gallery-container flex">
          <img
            v-for="(image, index) in images"
            class="gallery-img"
            :key="index"
            :src="image"
            @click="openModal(image)"
            alt="Фото"
          />

          <div v-if="modalImage" class="gallery-modal" @click="closeModal">
            <img class="gallery-modal__img" :src="modalImage" />
          </div>
        </div>

        <button @click="toggleMore" class="gallery-button flex">
          {{ !isMoreLoaded ? "Показать ещё" : "Скрыть" }}
        </button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.gallery {
  padding: 50px 0;

  .gallery-wrap {
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .gallery-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin: 0 auto;
  }

  .gallery-img {
    max-width: 100%;
    height: auto;
    border-radius: 9px;
    cursor: pointer;
    transition: transform 0.3s ease-in-out;

    &:hover {
      transform: scale(1.05);
    }
  }

  .gallery-modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;

    &__img {
      max-width: 90%;
      max-height: 90%;
      object-fit: contain;
      border-radius: 9px;
      transition: transform 0.3s ease-in-out;
    }
  }

  .gallery-button {
    width: 160px;
    height: 48px;
    margin-top: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 16px;
    font-weight: 500;
    color: #fff;
    background: transparent;
    border: 1px solid #fff;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out;

    &:hover {
      background-color: #464646;
    }
  }
}

@media (max-width: 1024px) {
  .gallery-container {
    gap: 10px !important;
  }

  .gallery-img {
    width: calc(50% - 20px);
  }
}

@media (max-width: 600px) {
  .gallery-modal__img {
    max-width: 95%;
    max-height: 80%;
  }

  .gallery-button {
    width: 100%;
  }
}
</style>
