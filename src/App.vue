<template>
  <div class="black-bg" v-if="modalState">
    <div class="white-bg">
      <h4>상세 페이지 제목</h4>
      <p>상세 페이지 내용</p>
      <button @click="modalState = false" class="t-center">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu" href="">{{ menu }}</a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <div v-for="(product, i) in products" :key="i"> -->
    <!-- <img
      :src="require('./assets/img/img' + (i + 1) + '.jpg')"
      alt="이미지"
      class="room-img"
    />
    <h4 @click="modalState = true">{{ product }}</h4>
    <p>가격</p>
    <button @click="increaseCnt(i)">카운터</button> -
    <span>클릭 횟수 : {{ alertCnt[i] }}</span> -->
  <!-- </div> -->

  <div v-for="(product, index) in exProducts" :key="index">
    <img :src="product.image" alt="이미지">
    <h4>{{product.title}}</h4>
    <p>{{product.price}}</p>
  </div>
</template>

<script>
import { exProducts } from "./assets/data/products.js";

export default {
  name: "App",
  data() {
    return {
      //화면에서 사용할 데이터 설정
      menus: ["Home", "Products", "About"],
      products: ["역삼동 ", "천호동", "마포구"],
      alertCnt: [0, 0, 0],
      modalState: false,
      exProducts: exProducts,
    };
  },
  methods: {
    increaseCnt(index) {
      this.alertCnt[index]++;
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkgrey;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 30%;
  margin-top: 2em;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: #ffffff;
  border-radius: 8px;
  padding: 20px;
}

.t-center {
  text-align: center;
}
</style>
