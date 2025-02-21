<script setup>
const images = [
  { src: "/img/logos_apple-app-store.png", alt: "Лого" },
  { src: "/img/logos_apiary.png", alt: "Лого" },
  { src: "/img/logos_android-icon.png", alt: "Лого" },
  { src: "/img/logos_basecamp.png", alt: "Лого" },
  { src: "/img/logos_airbnb.png", alt: "Лого" },
  { src: "/img/blender-orange.png", alt: "Лого" },
  { src: "/img/logos_ibm.png", alt: "Лого" },
];
</script>

<template>
  <div class="partners padding">
    <div class="wrapper">
      <div class="compnent-block-title flex">
        <h2 class="component-title">Партнёры</h2>
        <p class="compnent-about">
          Мы уделяем особое внимание эргономике и стараемся соответствовать
          месту работы
        </p>
      </div>
      <div class="partners-container flex">
        <div v-for="(image, index) in images" :key="index" class="partners-img">
          <img :src="image.src" alt="image.alt" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.partners-container {
  margin-top: 50px;
  justify-content: center;
  flex-wrap: wrap;
  gap: 40px;
}
</style>