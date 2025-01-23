<script>
export default {

  data() {
    return {
       isShowRegForm: false,
    };
  },

  methods: {
    showRegForm() {
      this.isShowRegForm = !this.isShowRegForm;
    }
  }
}
</script>

<template>
  <header>
  </header>

  <main>
    <div class="hello">
      <label class="hello-label">Олимпиада 2025</label>
    </div>

    <button class="reg-button" @click="showRegForm">Записаться</button>

    <div v-if="isShowRegForm" class="reg-form">
      <h1>Регистрация</h1>

      <button class="close-button" @click="showRegForm">✕</button>

      <form style="text-align: right; width: 75%; margin-left: 10%;">

          <p>
            <label class="reg_label" for="last_name">Фамилия</label>
            <input class="reg_input" type="text" id="last_name" name="last_name" required/>  
          </p>
          <p>
            <label class="reg_label" for="name">Имя</label>
            <input class="reg_input" type="text" id="name" name="name" required/>  
          </p>
          <p>
            <label class="reg_label" for="middle_name">Отчество</label>
            <input class="reg_input" type="text" id="middle_name" name="middle_name" placeholder="*если есть"/>  
          </p>

          <p>
            <label class="reg_label" for="phone">Телефон </label>
            <input class="reg_input" type="phone" pattern="\+\d-\d{3}-\d{3}-\d{4}" placeholder="+X-XXX-XXX-XXXX" id="phone" name="phone" required/>  
          </p>

          <p>
            <label class="reg_label" for="region">Регион</label>
            <select class="reg_select" id="region" name="region" required>
              <option disabled selected>Выберите регион</option>
              <option value="Moscow">Москва</option>
              <option value="Saint-Petersburg">Санкт-Петербург</option>
              <option value="Yaroslavl-Region" >Ярославская область</option>
              <option value="Vologda-Region">Вологодская область</option>
            </select>   
          </p>

          <input class="reg-form-button" type="submit" value="Зарегистрироваться" />
      </form>
    </div>
  </main>
</template>

<style scoped>
  .hello {
    background: -webkit-linear-gradient(#6aff00, #00b7ff);
    background-clip: text;
    -webkit-text-fill-color: transparent;
    border-width: 2px;
    border-color: rgb(58, 128, 141);
    border-style: groove;
    border-radius: 30px;
    width: 600px;
    height: 100px;
    text-align: center;
    align-content: center;
    position: absolute;
    margin-left: -20%;
    margin-top: -10%;
  }

  .hello-label {
    font-size: 56px;
    top: 100px;
  }

  .reg-form {
    background-color: rgb(58, 128, 141);
    width: 400px;
    height: 550px;
    margin-top: -20%;
    margin-left: -13%;
    position: absolute;
    border-radius: 30px;
    border-style: groove;
    border-width: 2px;
    border-color: #0c0d0d;
  }

  h1 {
    text-align: center;
    color: white;
    margin-top: 18px;
  }

  .close-button {
    position: absolute; /* Устанавливаем абсолютное позиционирование для кнопки */
    top: 13px; /* Отступ от верхнего края */
    right: 13px; /* Отступ от правого края */
    height: 25px;
    width: 25px;
    background: none;
    color: white; /* Белый цвет текста */
    border: none; /* Без рамки */
    border-radius: 4px; /* Закругленные углы */
    padding: 0px 0px; /* Внутренний отступ */
    cursor: pointer; /* Указатель при наведении */
    font-size: 14px; /* Размер шрифта */
    font-weight: 1000;
  }

  .close-button:hover {
    background-color: red;
  }

  .reg_label{
    color: white;
    font-size: 16px;
  }

  .reg_input {
    margin-top: 10px;
    margin-left: 10px;
  }

  .reg_select {
    width: 57%;
    height: 30px;
    margin-top: 15px;
    margin-left: 10px;
  }

  .reg-form-button {
    position: absolute;
    margin-top: 70%;
    margin-left: -50%;

    align-items: center;
    padding: 6px 14px;
    font-family: -apple-system, BlinkMacSystemFont, 'Roboto', sans-serif;
    border-radius: 6px;
    border: none;
    color: #fff;
    background: linear-gradient(180deg, #4B91F7 0%, #367AF6 100%);
    background-origin: border-box;
    box-shadow: 0px 0.5px 1.5px rgba(54, 122, 246, 0.25), inset 0px 0.8px 0px -0.25px rgba(255, 255, 255, 0.2);
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
  }

  .reg-form-button:focus {
    box-shadow: inset 0px 0.8px 0px -0.25px rgba(255, 255, 255, 0.2), 0px 0.5px 1.5px rgba(54, 122, 246, 0.25), 0px 0px 0px 3.5px rgba(58, 108, 217, 0.5);
    outline: 0;
  }

  .reg-button {
    align-items: center;
    appearance: none;
    background-clip: padding-box;
    background-color: initial;
    background-image: none;
    border-style: none;
    box-sizing: border-box;
    color: #fff;
    cursor: pointer;
    display: inline-block;
    flex-direction: row;
    flex-shrink: 0;
    font-family: Eina01,sans-serif;
    font-size: 16px;
    font-weight: 800;
    justify-content: center;
    line-height: 24px;
    margin: 0;
    min-height: 64px;
    outline: none;
    overflow: visible;
    padding: 19px 26px;
    pointer-events: auto;
    position: relative;
    text-align: center;
    text-decoration: none;
    text-transform: none;
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
    vertical-align: middle;
    width: auto;
    word-break: keep-all;
    z-index: 0;
    margin-left: -60%;
  }

  @media (min-width: 768px) {
    .reg-button {
      padding: 19px 32px;
    }
  }

  .reg-button:before,
  .reg-button:after {
    border-radius: 80px;
  }

  .reg-button:before {
    background-image: linear-gradient(90deg, rgb(0, 111, 78) 0%, rgba(0,111,101,1) 41%, rgba(0,139,132,1) 62%, rgba(0,159,155,1) 87%, rgba(0,230,235,1) 100%);
    content: "";
    display: block;
    height: 100%;
    left: 0;
    overflow: hidden;
    position: absolute;
    top: 0;
    width: 100%;
    z-index: -2;
  }

  .reg-button:after {
    background-color: initial;
    background-image: linear-gradient(90deg, rgb(0, 123, 86) 0%, rgb(0, 143, 131) 41%, rgba(0,139,132,1) 62%, rgba(0,159,155,1) 87%, rgba(0,230,235,1) 100%);
    bottom: 4px;
    content: "";
    display: block;
    left: 4px;
    overflow: hidden;
    position: absolute;
    right: 4px;
    top: 4px;
    transition: all 100ms ease-out;
    z-index: -1;
  }

  .reg-button:hover:not(:disabled):before {
    background: linear-gradient(90deg, rgb(0, 143, 100) 0%,rgba(0,230,235,1) 100%);
  }

  .reg-button:hover:not(:disabled):after {
    bottom: 0;
    left: 0;
    right: 0;
    top: 0;
    transition-timing-function: ease-in;
    opacity: 0;
  }

  .reg-button:active:not(:disabled) {
    color: #ccc;
  }

  .reg-button:active:not(:disabled):before {
    background-image: linear-gradient(0deg, rgba(0, 0, 0, .2), rgba(0, 0, 0, .2)), linear-gradient(90deg, rgb(0, 143, 100) 0%,rgba(0,230,235,1) 100%);
  }

  .reg-button:active:not(:disabled):after {
    background-image: linear-gradient(#541a0f 0, #0c0d0d 100%);
    bottom: 4px;
    left: 4px;
    right: 4px;
    top: 4px;
  }

  .reg-button:disabled {
    cursor: default;
    opacity: .24;
  }
</style>
