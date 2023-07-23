<script>
export default {
  props: {
    TogglePopup: Function,
    randomPost: Object,
  },
};
</script>
<template>
  <div class="popup">
    <div class="popup__inner">
      <slot />
      <h1 class="popup__title">Сегодня обедаем тут:</h1>
      <p class="popup__name">{{ randomPost.name }}</p>
      <img
        v-if="randomPost.photo != ''"
        :src="randomPost.photo"
        class="popup__image"
        alt=""
      />
      <img
        v-else
        class="popup__image"
        src="https://upload.wikimedia.org/wikipedia/commons/1/14/No_Image_Available.jpg?20200913095930"
        alt=""
      />
      <p v-if="randomPost.address != ''" class="popup__address">
        {{ randomPost.address }}
      </p>
      <p v-else class="popup__address">Нет адреса</p>

      <div>
        <button class="popup__button" @click="TogglePopup()">Закрыть</button>
      </div>
    </div>
  </div>
</template>
<style scoped>
.popup {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 99;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
}

.popup__inner {
  text-align: center;
  background-color: aliceblue;
  padding: 20px 300px 40px;
}

.popup__title {
  font-size: 30px;
  margin-bottom: 5px;
}

.popup__name {
  font-size: 27px;
  font-weight: 500;
  margin-top: 10px;
  margin-bottom: 20px;
}

.popup__image {
  width: 250px;
  height: 250px;
  margin-bottom: 10px;
}

.popup__address {
  font-size: 20px;
  margin-bottom: 20px;
}

.popup__button {
  margin: 0 auto;
  display: block;
  margin-bottom: 10px;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  background: rgb(40, 40, 40);
  background: linear-gradient(
    90deg,
    rgb(41, 41, 41) 0%,
    rgb(40, 40, 51) 0%,
    rgb(83, 83, 83) 100%
  );
  color: aliceblue;
  font-size: 25px;
}

.popup__button:hover {
  background: rgb(29, 29, 29);
  background: linear-gradient(
    90deg,
    rgb(27, 27, 27) 0%,
    rgb(22, 22, 26) 0%,
    rgb(62, 62, 62) 100%
  );
}

.popup__button:active {
  background: rgb(0, 0, 0);
  background: linear-gradient(
    90deg,
    rgb(0, 0, 0) 0%,
    rgb(0, 0, 0) 0%,
    rgb(0, 0, 0) 100%
  );
}

@media screen and (max-width: 1190px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 17px 250px 35px;
  }

  .popup__title {
    font-size: 27px;
    margin-bottom: 5px;
  }

  .popup__name {
    font-size: 25px;
    font-weight: 500;
    margin-top: 7px;
    margin-bottom: 15px;
  }

  .popup__image {
    width: 230px;
    height: 230px;
    margin-bottom: 7px;
  }

  .popup__address {
    font-size: 18px;
    margin-bottom: 18px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 7px 17px;
    font-size: 23px;
  }
}

@media screen and (max-width: 1030px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 14px 200px 28px;
  }

  .popup__title {
    font-size: 23px;
    margin-bottom: 5px;
  }

  .popup__name {
    font-size: 20px;
    font-weight: 500;
    margin-top: 5px;
    margin-bottom: 12px;
  }

  .popup__image {
    width: 200px;
    height: 200px;
    margin-bottom: 5px;
  }

  .popup__address {
    font-size: 16px;
    margin-bottom: 16px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 5px 15px;
    font-size: 20px;
  }
}

@media screen and (max-width: 930px) {
}

@media screen and (max-width: 840px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 12px 170px 23px;
  }

  .popup__title {
    font-size: 21px;
    margin-bottom: 4px;
  }

  .popup__name {
    font-size: 18px;
    font-weight: 500;
    margin-top: 4px;
    margin-bottom: 10px;
  }

  .popup__image {
    width: 180px;
    height: 180px;
    margin-bottom: 5px;
  }

  .popup__address {
    font-size: 16px;
    margin-bottom: 16px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 5px 15px;
    font-size: 20px;
  }
}

@media screen and (max-width: 735px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 10px 150px 20px;
  }

  .popup__title {
    font-size: 20px;
    margin-bottom: 4px;
  }

  .popup__name {
    font-size: 17px;
    font-weight: 500;
    margin-top: 4px;
    margin-bottom: 10px;
  }

  .popup__image {
    width: 170px;
    height: 170px;
    margin-bottom: 5px;
  }

  .popup__address {
    font-size: 15px;
    margin-bottom: 15px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 5px 15px;
    font-size: 20px;
  }
}

@media screen and (max-width: 625px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 6px 110px 18px;
  }

  .popup__title {
    font-size: 18px;
    margin-bottom: 4px;
  }

  .popup__name {
    font-size: 16px;
    font-weight: 500;
    margin-top: 4px;
    margin-bottom: 10px;
  }

  .popup__image {
    width: 160px;
    height: 160px;
    margin-bottom: 5px;
  }

  .popup__address {
    font-size: 15px;
    margin-bottom: 14px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 5px 15px;
    font-size: 20px;
  }
}

@media screen and (max-width: 520px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 6px 80px 12px;
  }

  .popup__title {
    font-size: 16px;
    margin-bottom: 4px;
  }

  .popup__name {
    font-size: 14px;
    font-weight: 500;
    margin-top: 4px;
    margin-bottom: 8px;
  }

  .popup__image {
    width: 120px;
    height: 120px;
    margin-bottom: 5px;
  }

  .popup__address {
    font-size: 15px;
    margin-bottom: 14px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 5px 15px;
    font-size: 15px;
  }
}

@media screen and (max-width: 440px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 4px 60px 8px;
  }

  .popup__title {
    font-size: 14px;
    margin-bottom: 4px;
  }

  .popup__name {
    font-size: 12px;
    font-weight: 500;
    margin-top: 4px;
    margin-bottom: 8px;
  }

  .popup__image {
    width: 100px;
    height: 100px;
    margin-bottom: 5px;
  }

  .popup__address {
    font-size: 10px;
    margin-bottom: 10px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 5px 15px;
    font-size: 10px;
  }
}

@media screen and (max-width: 370px) {
  .popup__inner {
    text-align: center;
    background-color: aliceblue;
    padding: 2px 40px 6px;
  }

  .popup__title {
    font-size: 12px;
    margin-bottom: 3px;
  }

  .popup__name {
    font-size: 10px;
    font-weight: 500;
    margin-top: 4px;
    margin-bottom: 8px;
  }

  .popup__image {
    width: 70px;
    height: 70px;
    margin-bottom: 4px;
  }

  .popup__address {
    font-size: 8px;
    margin-bottom: 8px;
  }

  .popup__button {
    margin: 0 auto;
    display: block;
    margin-bottom: 10px;
    padding: 3px 10px;
    font-size: 8px;
  }
}
</style>
