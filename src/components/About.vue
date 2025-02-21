<script setup>
</script>

<template>
  <div class="about">
    <div class="wrapper">
      <div class="about-container flex">
        <div class="about-container-descr flex">
          <p class="about-title">Работай быстрее скорости мысли</p>
          <p class="about-descr">
            Большинство календарей предназначены для команд. Link предназначен
            для фрилансеров, которым нужен простой способ планирования своего
            расписания.
          </p>
          <div class="about-buttons flex">
            <button class="button-fry flex">Попробовать бесплатно</button>
            <button class="button-more flex">Узнать больше</button>
          </div>
        </div>

        <div class="about-img-container">
          <img
            class="about-img"
            src="@/assets/img/dashboard.png"
            alt="Dashboard"
          />
        </div>
      </div>
    </div>
    <div class="image-filter"></div>
  </div>
</template>

<style lang="scss" scoped>
.about {
  position: relative;
  background-color: #16181d;
  overflow: hidden;
  padding: 80px 20px;

  .about-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;

    .about-container-descr {
      max-width: 700px;
      padding: 80px 0;
      display: flex;
      flex-direction: column;
      align-items: center;

      .about-title {
        margin-bottom: 30px;
        font-size: 60px;
        line-height: 1.2;
        font-weight: 600;
        color: #fff;
      }

      .about-descr {
        margin-bottom: 40px;
        font-size: 20px;
        line-height: 1.5;
        font-weight: 500;
        color: #e2e4e9;
      }

      .about-buttons {
        display: flex;
        justify-content: center;
        gap: 16px;

        .button-fry,
        .button-more {
          height: 56px;
          padding: 0 20px;
          display: flex;
          align-items: center;
          justify-content: center;
          font-size: 18px;
          font-weight: 500;
          color: #fff;
          border-radius: 8px;
          cursor: pointer;
          transition: all 0.3s ease-in-out;
        }

        .button-fry {
          width: 250px;
          background-color: #4452fe;
          border: 1px solid #4452fe;
        }

        .button-fry:hover {
          background-color: #6975fe;
          border-color: #fff;
        }

        .button-more {
          width: 180px;
          background-color: transparent;
          border: 1px solid #fff;
        }

        .button-more:hover {
          background-color: #464646;
        }
      }
    }

    .about-img-container {
      max-width: 900px;
      width: 100%;
      margin-top: 40px;
      display: flex;
      justify-content: center;
    }

    .about-img {
      width: 100%;
      height: auto;
      object-fit: contain;
    }
  }

  .image-filter {
    width: 100%;
    height: 25%;
    position: absolute;
    left: 0;
    bottom: 0;
    background: linear-gradient(to top, rgba(0, 0, 0, 1), rgba(0, 0, 0, 0));
  }
}

@media (max-width: 1024px) {
  .about {
    padding: 60px 15px;
  }

  .about-container-descr {
    padding: 60px 0;

    .about-title {
      font-size: 50px !important;
    }

    .about-descr {
      font-size: 18px;
    }
  }
}

@media (max-width: 768px) {
  .about-title {
    font-size: 40px;
  }
  .about-container-descr {
    padding: 50px 0;

    .about-title {
      font-size: 42px !important;
    }

    .about-descr {
      font-size: 16px;
    }
  }

  .about-buttons {
    flex-direction: column;
    gap: 12px;

    .button-fry,
    .button-more {
      width: 100%;
    }
  }

  .about .about-container .about-container-descr .about-buttons .button-more {
    width: 250px;
  }
}

@media (max-width: 480px) {
  .about {
    padding: 40px 10px;
  }

  .about-container-descr {
    padding: 40px 0;

    .about-title {
      font-size: 36px !important;
    }

    .about-descr {
      font-size: 14px;
    }
  }

  .about-buttons {
    flex-direction: column;
    gap: 10px;
  }
}
</style>
