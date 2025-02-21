<script setup>
import { ref } from "vue";

const phone = ref("+7 ");
const email = ref("");
const emailError = ref("");

const onFocus = () => {
  if (!phone.value.startsWith("+7")) {
    phone.value = "+7 ";
  }
};

const onInput = (event) => {
  let value = event.target.value.replace(/[^\d\s()-]/g, "");

  if (!value.startsWith("+7")) {
    phone.value = "+7 ";
  } else {
    phone.value = value;
  }
};

const onKeyDown = (event) => {
  if (event.key === "Backspace" && event.target.selectionStart <= 3) {
    event.preventDefault();
  }
};

const validateEmail = () => {
  const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  emailError.value = emailPattern.test(email.value)
    ? ""
    : "Введите корректный email";
};
</script>

<template>
  <div class="form">
    <div class="wrapper">
      <div class="form-container flex">
        <div class="form-descr">
          <div class="form-descr-wrap">
            <p class="form-descr__title">Оставьте заявку на бетатест</p>
            <p class="form-descr__text">
              Мы уделяем особое внимание эргономике и стараемся соответствовать
              месту работы
            </p>
          </div>
        </div>

        <div class="form-form">
          <form action="/submit-form" method="POST" class="form">
            <div class="form-group flex">
              <label class="form-label" for="name">Ваше имя</label>
              <input
                class="form-input"
                type="text"
                id="name"
                name="name"
                required
                placeholder="Иван"
              />
            </div>

            <div class="form-group flex">
              <label class="form-label" for="phone">Номер телефона</label>
              <input
                class="form-input"
                type="tel"
                id="phone"
                name="phone"
                v-model="phone"
                @focus="onFocus"
                @input="onInput"
                @keydown="onKeyDown"
                placeholder="+7 000 000-00-00"
                required
              />
            </div>

            <div class="form-group flex">
              <label class="form-label" for="email">E-mail</label>
              <input
                class="form-input"
                type="email"
                id="email"
                name="email"
                v-model="email"
                @input="validateEmail"
                placeholder="example@email.com"
                required
              />
              <p v-if="emailError" class="error-message">{{ emailError }}</p>
            </div>

            <div class="form-group flex">
              <label class="textarea-label" for="message"
                >Комментарий к заявке</label
              >
              <textarea
                class="form-textarea"
                id="message"
                name="message"
                rows="5"
                placeholder="Здравствуйте, хотелось бы..."
              ></textarea>
            </div>

            <p class="form-warning">
              Нажимая «Отправить» вы соглашаетесь с<br />
              <span class="form-warning__bottom"
                >политикой конфиденциальности</span
              >
            </p>

            <div class="form-group">
              <button class="form-button flex" type="submit">Отправить</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.form-container {
  margin: 56px 0;
  display: flex;
  align-items: center;
  background-color: #22252b;
  border-radius: 8px;
  flex-wrap: wrap;

  .form-descr {
    flex: 1;
    height: 100%;
    min-height: 652px;
    padding: 40px;
    background-color: #4452fe;
    border-radius: 8px 0 0 8px;
    position: relative;
    overflow: hidden;
    display: flex;
    justify-content: center;
    background-image: url(/src/assets/img/dashboard.png);
    background-repeat: no-repeat;
    background-position: -240px 250px;
    background-size: cover;

    .form-descr-wrap {
      max-width: 492px;

      .form-descr__title {
        margin-bottom: 24px;
        font-size: 48px;
        font-weight: 600;
        color: #fff;
        text-align: center;
      }

      .form-descr__text {
        font-size: 18px;
        font-weight: 400;
        color: #fff;
        text-align: center;
      }
    }
  }

  .form-form {
    flex: 1;
    width: 100%;
    padding: 40px;
    display: flex;
    justify-content: center;

    .form {
      width: 100%;

      .form-group {
        margin-bottom: 20px;
        display: flex;
        flex-direction: column;

        .form-label,
        .textarea-label {
          margin-bottom: 5px;
          font-size: 16px;
          font-weight: 400;
          color: #fff;
        }

        .form-input,
        .form-textarea {
          padding: 12px 16px;
          font-size: 16px;
          border-radius: 8px;
          background-color: #2d3139;
          border: none;
          color: #fff;
        }

        .form-textarea {
          resize: none;
        }
      }

      .form-warning {
        font-size: 14px;
        color: #707a8f;
        text-align: left;

        &__bottom {
          text-decoration: underline;
        }
      }

      .form-button {
        margin-top: 40px;
        width: 100%;
        padding: 14px;
        border-radius: 8px;
        background-color: #4452fe;
        color: #fff;
        font-size: 16px;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        transition: background 0.3s;
        border: none;
      }

      .form-button:hover {
        background-color: #6975fe;
      }
    }
  }

  .error-message {
    color: red;
    font-size: 14px;
    margin-top: 4px;
  }
}

@media (max-width: 1024px) {
  .form-container {
    flex-direction: column;

    .form-descr {
      border-radius: 8px 8px 0 0;
      height: auto;
      padding: 30px;
      width: 100%;
    }
  }
}

@media (max-width: 768px) {
  .form-descr__title {
    font-size: 36px;
  }

  .form-descr__text {
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  .form-form {
    padding: 40px 0 !important;
  }

  .form-descr {
    padding: 20px;
  }

  .form-button {
    font-size: 14px;
    padding: 12px;
  }
}
</style>
