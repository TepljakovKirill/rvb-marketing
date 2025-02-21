<script setup>
</script>

<template>
  <div class="product">
    <div class="wrapper">
      <div class="compnent-block-title flex">
        <h2 class="component-title">Продукт</h2>
        <p class="compnent-about">
          Мы уделяем особое внимание эргономике и стараемся соответствовать
          месту работы
        </p>
      </div>

      <div class="product-container flex">
        <div class="product-container__item flex">
          <p class="product-container__title">Работа</p>
          <p class="product-container__text">
            Вы когда-нибудь задумывались о том, не слишком ли вы зависите от
            клиента в работе? Link поможет вам определиться
          </p>
          <div class="product-container__button">
            <button class="button">Регистрация</button>
          </div>
          <div class="product-container__img">
            <img src="@/assets/img/Macbook.png" alt="Macbook" />
          </div>
        </div>

        <div class="product-container__item flex">
          <p class="product-container__title">Дизайн с реальными данными</p>
          <p class="product-container__text">
            Вы когда-нибудь задумывались о том, не слишком ли вы зависите от
            клиента в работе? Link поможет вам определиться
          </p>
          <div class="product-container__button">
            <button class="button">Попороовать бесплатно</button>
          </div>

          <div class="product-container__img">
            <img
              src="@/assets/img/Boards-Notifications.png"
              alt="Boards-Notifications"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.product-container {
  margin-top: 55px;
  padding-bottom: 100px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;

  &__item {
    width: calc(50% - 10px);
    display: flex;
    flex-direction: column;
    text-align: center;
    align-items: center;
    background-color: #22252b;
    border-radius: 16px;
    padding: 43px 20px;
  }

  &__title {
    margin-bottom: 20px;
    font-size: 20px;
    font-weight: 500;
    color: #fff;
  }

  &__text {
    max-width: 366px;
    margin: 0 auto;
    font-size: 16px;
    font-weight: 400;
    color: #e2e4e9;
  }

  &__img {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px auto 0;

    img {
      max-width: 100%;
      height: auto;
    }
  }

  .button {
    margin-top: 42px;
    padding: 12px 24px;
    font-size: 16px;
    font-weight: 500;
    color: #fff;
    background-color: #4452fe;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out;
  }

  .button:hover {
    background-color: #6975fe;
  }
}

@media (max-width: 890px) {
  .product-container {
    flex-direction: column;
    align-items: center;
  }

  .product-container__item {
    width: 90%;
    padding: 30px 15px;
  }
}

@media (max-width: 480px) {
  .product-container__text {
    font-size: 14px;
  }

  .button {
    width: 100%;
    padding: 14px;
  }
}
</style>