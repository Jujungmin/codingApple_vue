<template>
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> <!-- vue반복문 :: <태그 v-for="작명 in 몇회 || 데이터도가능 " :key="작명"> -->
    <!-- '메뉴들' 데이터 안에 있던 데이터들이 'a'변수 안에 들어감 => 반복문 돌려짐 -->
    <!--
      * vue 반복문 특)
      array/object에 집어넣기 가능
      => 그럼 자료안의 데이터 갯수만큼 반복됨
      => 그럼 작명한 변수는 데이터안의 자료가 됨
      => 변수 작명2개까지 가능 v-for="(a,i) in 메뉴들" :key="i" a는 Home/Products/Abojt i는 0/1/2
    -->
    <!-- 
      * :key="" 용도
      - 반복문 쓸 때 꼭 써야함
      - 반복문 돌린 요소를 컴퓨터가 구분하기 위해 씀
      여기서 a 는 0 1 2.. 
     -->
  </div>
  <!--
  <div>
    <h4 class="red" :style="스타일">{{ products[0] }}</h4> !-- :속성="데이터이름" --
    <p>40 만원</p> !-- 밑에 있는 데이터 넣고 싶다면 {{ 자료이름 }} --
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>70 만원</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>100 만원</p>
  </div>
  -->

  <div v-for="(a,i) in products" :key="i">
    <!-- <h4>{{ products[i] }}</h4> -->
    <h4>{{ a }}</h4> <!-- a는 products 자료들 -->
    <p>{{ price[i] }} 만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  // data() 데이터 보관함
  data() {
    return {
      // return 안에 데이터가 있음
      // 데이터는 object자료로 저장 {자료이름 : 자료내용}
      // price1 : 40,
      // price2 : 70,
      // 스타일 : 'color : red',
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      메뉴들 : ['Home', 'Products', 'About'],
      price : [40, 70, 100]
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {margin:0;}
.menu {background:darkslateblue; padding: 15px; border-radius:5px;}
.menu a {color: #fff; padding:10px;}
div {box-sizing:border-box;}
.black-bg {width:100%; height:100%; background:rgba(0,0,0,0.5); position:fixed; top:0; padding:20px;}
.white-bg {width:100%; background:#fff; border-radius:8px; padding:20px;}

</style>

<!-- 
  {{데이터바인딩}} 하는 이유.
  HTML에 하드코딩해놓으면 나중에 변경이 어려움.(가변적인 데이터나 자주변할거같은 데이터) / 고정적인 부분은 굳이 데이터바인딩안해도 된다.
  vue의 실시간 자동렌더링 가능(vue는 data와 관련된 HTML에도 실시간 재렌더링 가능)

 -->