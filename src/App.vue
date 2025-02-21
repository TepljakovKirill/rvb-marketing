<script setup>
import Header from "./components/Header.vue";
import About from "./components/About.vue";
import Advantages from "./components/Advantages.vue";
import Product from "./components/Product.vue";
import Gallery from "./components/Gallery.vue";
import Partners from "./components/Partners.vue";
import Reviews from "./components/Reviews.vue";
import Form from "./components/Form.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <Header />
  <main>
    <About />
    <section id="advantages">
      <Advantages />
    </section>

    <section id="product">
      <Product />
    </section>

    <section id="gallery">
      <Gallery />
    </section>

    <section id="partners">
      <Partners />
    </section>

    <section id="reviews">
      <Reviews />
    </section>
  </main>
  <Footer />
</template>

<style scoped>
</style>