<template>
<div>
  <Modal @closeModal="modalState = true" :data="data" :index="index" :modalState="modalState"/>
  <div class="menu">
    <a v-for="(item, idx) in menu" :key="idx">{{item}}</a>
  </div>
  

  <Discount/>

  <Card @openModal="modalState = false; index = $event"  :data="data[idx]" :modalState="modalState" v-for="(item, idx) in data" :key="idx"/>
  <!-- : 안붙이면 문자로 전달된다, 요청은 부탁에 맞게 할일을 해준다, 자료를 받는다-->

  
  
</div>

</template>

<script>
import data from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data() {
    return {
      index : 0,
      data: data,
      price1 : 60,
      price2 : 70,
      gray: 'gray',
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menu : ['Home', 'Shop', 'About'],
      count : [0, 0, 0],
      modalState: true
      }
    },
    methods : {
      increase(e) {
        console.log(e)
        this.count[0] += 1;
        
      }
    },
    components: {
      Discount,
      Modal,
      Card
    }
}
</script>

<style lang="css">
  @import './css/style.css';
</style>
<!--<style>
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.gray {color: gray;}
.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}
</style> -->
