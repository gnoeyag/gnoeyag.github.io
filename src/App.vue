<template>
<!--   <div class="black-bg" v-if="isOpen === true">
    <div class="white-bg">
      <h4>상세페이지 제목</h4>
      <p>상세페이지 내용</p>
      <button @click="isOpen = false">닫기</button>
    </div>
  </div>

  <div v-for="(el, i) in data" :key="i">
    <img :src="el.image" class="product-image" />
    <h3 @click="isOpen = true" class="product-title">
      <a href="#">{{ el.title }}</a>
    </h3>
    <p>{{ el.price }} ₩</p>
    <p>{{ el.content }}</p>
    <button @click="num[i]++">매물신고</button>
    <p>신고 수 : {{ num[i] }}</p>
  </div> -->

  <!-- data 적용 전 -->
  <div v-for="(el, i) in products" :key="i">
    <img src="https://via.placeholder.com/300" class="room-image"/>
    <h4 @click="isOpen = true"><a href="#">{{ el }}</a></h4>
    <p>$ {{ price[i] }}</p>
    <button @click="num[i]++;">매물신고</button>
    <p>신고 수 : {{ num[i] }}</p>
  </div>
</template>

<script>
import data from "./assets/productList.js";

export default {
  name: "App",
  data() {
    return {
      isOpen: false,
      data: data,
      num: [0, 0, 0, 0, 0, 0],
      price: [6000, 3000, 5000],
      products: ["Product1", "Product2", "Product3"],
    };
  },
  methods: {
    increase() {
      this.num++;
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
  margin-top: 60px;
}

body {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}

a {
  text-decoration: none;
  color: black;
}

ul,
ol,
li {
  list-style: none;
}

div {
  box-sizing: border-box;
}

.product-title {
  margin-top: 40px;
}

.product-title a:hover {
  color: pink;
}

.product-image {
  margin-top: 40px;
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
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
