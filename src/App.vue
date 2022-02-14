
<template>

  <div class='black-bg' v-if="모달창==true">
    <div class='white-bg'>
      <h4>상세 페이지</h4>
      <p>상세 내용입니다. change</p>
      <button @click="close">닫기</button>
    </div>
  </div>
  <div class='menu'>
    <a v-for="i in 메뉴들" :key="i">{{ i }}</a>
  </div> 
    
    <b>원룸</b>
    <button type="button" v-on:click="hello">여기는</button>
  
   <div v-for="(i,j) in 원룸들" :key="j">
    <img :src="원룸들[j].image" class='room-image'>
    <h4 class='red' :style="스타일">{{ 원룸들[j].title}}</h4>
    <p>{{원룸들[j].price}}원</p>
  </div>
 
  
</template>

<script>

import data from './assets/data.js'


export default {
  name: 'App',
  data(){
    return {
      price1 : 60,
      price2 : 70,
      스타일 : 'color : blue',
      products : ['역삼동원룸', '천호동원룸','삼성동원룸'],
      메뉴들 : ['Home', 'Products', 'About'],
      신고수 : {'역삼':0, '천호':0, '삼성':0},
      모달창: false,
      원룸들 : data,
    }
  },
  methods :{
    increase(){
      this.신고수+=1;
    },
    close(){
      this.모달창= false
    },
    hello : function(){
      alert('안녕하세요 원룸샵입니다.');
    },
  },
  components: {
    
  }
}
</script>

<style>

body {
  margin:0
}
div {
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height:100px;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

.room-image{
  width: 100%;
  margin-top: 40px;
}


</style>
