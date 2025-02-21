<script setup>
</script>

<template>
  <div class="advantages padding">
    <div class="wrapper">
      <div class="compnent-block-title flex">
        <h2 class="component-title">Преимущества</h2>
        <p class="compnent-about">
          Link предназначен для фрилансеров, которым нужен простой способ
          планирования своего расписания
        </p>
      </div>
      <div class="advantages-container flex">
        <img class="advantages-img" src="@/assets/img/Chat.png" alt="Chat" />

        <div class="advantages-section">
          <div class="advantages-block flex">
            <div class="advantages-block__img">
              <img src="@/assets/img/seo-good.png" alt="seo-good" />
            </div>
            <div class="advantages-block__content">
              <h3 class="advantages-block__title">Единый источник истины</h3>
              <p class="advantages-block__descr">
                Когда вы добавляете работу в свой календарь Link, мы
                автоматически вычисляем полезные сведения
              </p>
            </div>
          </div>

          <div class="advantages-block flex">
            <div class="advantages-block__img">
              <img src="@/assets/img/site-template.png" alt="site-template" />
            </div>
            <div class="advantages-block__content">
              <h3 class="advantages-block__title">Интуитивный интерфейс</h3>
              <p class="advantages-block__descr">
                Когда вы добавляете работу в свой календарь Link, мы
                автоматически вычисляем полезные сведения
              </p>
            </div>
          </div>

          <div class="advantages-block flex">
            <div class="advantages-block__img">
              <img
                src="@/assets/img/chart-cube-arrow.png"
                alt="chart-cube-arrow"
              />
            </div>
            <div class="advantages-block__content">
              <h3 class="advantages-block__title">Без ограничений</h3>
              <p class="advantages-block__descr">
                Когда вы добавляете работу в свой календарь Link, мы
                автоматически вычисляем полезные сведения
              </p>
            </div>
          </div>

          <div class="advantages-block flex">
            <div class="advantages-block__img">
              <img src="@/assets/img/Union.png" alt="Union" />
            </div>
            <div class="advantages-block__content">
              <h3 class="advantages-block__title">Постоянная поддержка</h3>
              <p class="advantages-block__descr">
                Когда вы добавляете работу в свой календарь Link, мы
                автоматически вычисляем полезные сведения
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.advantages-container {
  padding-top: 100px;
  justify-content: center;
  flex-wrap: wrap;

  .advantages-img {
    width: 100%;
    max-width: 768px;
    height: auto;
    background-color: transparent;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .advantages-section {
    padding-top: 25px;
    display: flex;
    flex-direction: column;
    gap: 35px;

    .advantages-block {
      display: flex;
      align-items: flex-start;
      max-width: 336px;
      justify-content: space-between;

      &__content {
        padding-left: 25px;
      }

      &__img {
        width: 32px;
        height: 32px;
      }

      &__title {
        padding-bottom: 15px;
        font-size: 20px;
        font-weight: 500;
        color: #fff;
      }

      &__descr {
        font-size: 16px;
        font-weight: 400;
        line-height: 24px;
        color: #fff;
      }
    }
  }

  @media (max-width: 1024px) {
    padding-top: 50px;

    .advantages-img {
      max-width: 600px;
    }

    .advantages-section {
      flex-direction: column;
      align-items: center;
    }
  }

  @media (max-width: 768px) {
    .component-title {
      font-size: 15px !important;
    }

    padding-top: 30px;
    flex-direction: column;

    .advantages-img {
      max-width: 100%;
    }

    .advantages-section {
      gap: 20px;

      .advantages-block {
        max-width: 100%;
        flex-direction: row;

        &__content {
          padding-left: 15px;
        }

        &__title {
          font-size: 18px;
        }

        &__descr {
          font-size: 14px;
          line-height: 20px;
        }
      }
    }
  }

  @media (max-width: 480px) {
    .advantages-section {
      .advantages-block {
        &__content {
          padding-left: 15px;
        }
      }
    }
  }
}
</style>