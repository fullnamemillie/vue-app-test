<script>
import axios from 'axios';

import Header from './components/Header.vue';
import Popup from './components/Popup.vue';

export default {
  data() {
    return {
      posts: '',
      randomPost: '',
      isOpen: false,
    };
  },
  mounted() {
    axios.get('https://bandaumnikov.ru/api/test/site/get-index').then((res) => {
      this.posts = res.data.data;
    });
  },
  methods: {
    getRandomPost() {
      const randomPost = Math.floor(Math.random() * this.posts.length);
      this.randomPost = this.posts[randomPost];
    },
    togglePopup() {
      this.isOpen = !this.isOpen;
      this.getRandomPost();
    },
  },
  components: { Popup, Header },
};
</script>

<template>
  <div class="container">
    <Popup v-if="isOpen" :TogglePopup="togglePopup" :randomPost="randomPost" />
    <Header />
    <section class="block">
      <h1 class="title">Кафе в нашем городе на выбор</h1>
      <button class="button" @click="togglePopup">
        Выбрать случайное кафе
      </button>
      <div class="list__block">
        <ul class="list" v-for="post in posts">
          <li class="list__image">
            <img
              v-if="post.photo != ''"
              class="cafe__image"
              :src="post.photo"
              alt="cafe-image"
            />
            <img
              v-else
              class="cafe__image"
              src="https://upload.wikimedia.org/wikipedia/commons/1/14/No_Image_Available.jpg?20200913095930"
              alt="cafe-image"
            />
          </li>
          <li class="list__item">{{ post.name }}</li>
          <li v-if="post.address != ''" class="list__item">
            {{ post.address }}
          </li>
          <li v-else class="list__item">Нет адреса</li>
        </ul>
      </div>
    </section>
  </div>
</template>

<style scoped>
.container {
  width: 1160px;
  padding-left: 20px;
  padding-right: 20px;
  margin: 0 auto;
}

/*Main-content*/

.block {
  background-color: aliceblue;
  padding: 20px;
}

.title {
  text-align: center;
  font-size: 30px;
  margin-bottom: 30px;
}

.button {
  margin: 0 auto;
  display: block;
  margin-bottom: 50px;
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

.button:hover {
  background: rgb(29, 29, 29);
  background: linear-gradient(
    90deg,
    rgb(27, 27, 27) 0%,
    rgb(22, 22, 26) 0%,
    rgb(62, 62, 62) 100%
  );
}

.button:active {
  background: rgb(0, 0, 0);
  background: linear-gradient(
    90deg,
    rgb(0, 0, 0) 0%,
    rgb(0, 0, 0) 0%,
    rgb(0, 0, 0) 100%
  );
}

.list__block {
  display: flex;
  flex-wrap: wrap;
  gap: 26.5px;
}

.list {
  margin-bottom: 20px;
  width: 250px;
}

.list__item {
  list-style-type: none;
  padding-top: 3px;
  padding-bottom: 3px;
  text-align: center;
  font-size: 18px;
  list-style-type: none;
}

.list__image {
  list-style-type: none;
  width: 250px;
  height: 250px;
}

.cafe__image {
  width: 250px;
  height: 250px;
}

@media screen and (max-width: 1190px) {
  .container {
    width: 1000px;
  }

  .list__block {
    display: flex;
    flex-wrap: wrap;
    column-gap: 85px;
  }
}

@media screen and (max-width: 1030px) {
  .container {
    width: 900px;
  }

  .list__block {
    display: flex;
    flex-wrap: wrap;
    column-gap: 35px;
  }
}

@media screen and (max-width: 930px) {
  .container {
    width: 800px;
  }

  .list__block {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 2vw;
  }

  .list {
    width: 200px;
  }

  .list__image {
    list-style-type: none;
    width: 200px;
    height: 200px;
  }

  .cafe__image {
    width: 200px;
    height: 200px;
  }
}

@media screen and (max-width: 840px) {
  .container {
    width: 700px;
  }

  .list__block {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 2vw;
  }

  .list {
    width: 180px;
  }

  .list__image {
    list-style-type: none;
    width: 180px;
    height: 180px;
  }

  .cafe__image {
    width: 180px;
    height: 180px;
  }
}

@media screen and (max-width: 735px) {
  .container {
    width: 600px;
  }

  .list__block {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr 1fr;
  }

  .list {
    width: 250px;
  }

  .list__image {
    list-style-type: none;
    width: 250px;
    height: 250px;
  }

  .cafe__image {
    width: 250px;
    height: 250px;
  }
}

@media screen and (max-width: 625px) {
  .container {
    width: 500px;
  }

  .list__block {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr 1fr;
  }

  .list {
    width: 200px;
  }

  .list__image {
    list-style-type: none;
    width: 200px;
    height: 200px;
  }

  .cafe__image {
    width: 200px;
    height: 200px;
  }
}

@media screen and (max-width: 520px) {
  .container {
    width: 420px;
  }

  .list__block {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr;
  }

  .list {
    width: 300px;
  }

  .list__image {
    list-style-type: none;
    width: 300px;
    height: 300px;
  }

  .cafe__image {
    width: 300px;
    height: 300px;
  }
}

@media screen and (max-width: 440px) {
  .container {
    width: 340px;
  }

  .list__block {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr;
  }

  .list {
    width: 250px;
  }

  .list__image {
    list-style-type: none;
    width: 250px;
    height: 250px;
  }

  .cafe__image {
    width: 250px;
    height: 250px;
  }
}

@media screen and (max-width: 370px) {
  .container {
    width: 270px;
  }

  .list__block {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr;
  }

  .list {
    width: 180px;
  }

  .list__image {
    list-style-type: none;
    width: 180px;
    height: 180px;
  }

  .cafe__image {
    width: 180px;
    height: 180px;
  }
}
</style>
