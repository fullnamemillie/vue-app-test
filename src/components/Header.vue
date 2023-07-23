<script>
export default {};
</script>
<template>
  <header class="header">
    <img
      class="header__image"
      src="https://htmlcolorcodes.com/assets/images/colors/hot-pink-color-solid-background-1920x1080.png"
      alt="color"
    />
    <p class="header__title">Приложение для случайного выбора кухни</p>
  </header>
</template>
<style scoped>
.header {
  display: flex;
  align-items: center;
  gap: 20px;
  font-size: 20px;
  padding: 20px;
  background-color: aliceblue;
  margin-top: 20px;
  margin-bottom: 20px;
}

.header__image {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}

.header__title {
  font-size: 22px;
  font-weight: 400;
}

@media screen and (max-width: 930px) {
  .header {
    gap: 10px;
  }
  .header__image {
    width: 30px;
    height: 30px;
  }

  .header__title {
    font-size: 16px;
  }
}

@media screen and (max-width: 735px) {
  .header {
    justify-content: center;
    gap: 15px;
  }
  .header__image {
    width: 40px;
    height: 40px;
  }

  .header__title {
    font-size: 20px;
  }
}

@media screen and (max-width: 625px) {
  .header {
    justify-content: center;
    gap: 10px;
  }
  .header__image {
    width: 30px;
    height: 30px;
  }

  .header__title {
    font-size: 16px;
  }
}
</style>
