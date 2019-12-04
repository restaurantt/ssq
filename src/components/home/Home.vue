<template>
  <div class="home">
    <div>
      <ul>
      <li><BallsView v-bind:redArray = redsArray v-bind:blue = blueNum /></li>
      </ul>
    </div>
    <div id="randombtn" class="anim animat">
      <button class="button" v-on:click="randomaction">随机</button>
    </div>
  </div>
</template>

<script type="text/javascript">
import BallsView from '../common/BallsView.vue'

export default {
  name: 'Home',
  props: {
    msg: String
  },
  components: {
    BallsView
  },
  data: function () {
    return {
      redsArray : [1,2,3,4,5,6],
      blueNum : 7
    }
  },
  watch: {
    redsArray: function() {

    },
    blueNum: function() {

    }
  },
  created: function() {

  },
  mounted: function() {

  },
  methods: {
    randomaction: function() {
      this.redsArray = generateReds()
      this.blueNum = getRandomNumber(false)
    }
  }
}

function generateReds() {
  var tempRedArray = new Set()

  do {
    var num = getRandomNumber(true)
    tempRedArray.add(num)
  } while (tempRedArray.size < 6)
  var sortedArray = Array.from(tempRedArray).sort((a, b) => a - b)
  return sortedArray
}

function getRandomNumber(isRed) {
  if (isRed) {
    return Math.floor(Math.random()*33)+1
  } else {
    return Math.floor(Math.random()*16)+1
  }
}

// 缩放按钮
// var i = 0;
//
// self.setInterval(clock,700);
//
// function clock(){
//   i++;
//   if(parseInt(i/2) == i/2){
//     //this.isZoomSmall = false;
//     this.isZoomBig = true;
//     // document.getElementById('randombtn').addClass("anim-show");
//     // document.getElementById('randombtn').removeClass("anim-show1");
//   }else{
//     // document.getElementById('randombtn').removeClass("anim-show");
//     // document.getElementById('randombtn').addClass("anim-show1");
//     //this.isZoomSmall = true;
//     this.isZoomBig = false;
//   }
// }


</script>

<style>
.anim{
    width: 100px;
    height: 60px;
    background-color: green;
    text-align: center;
    border-radius:10px;
    margin:0 auto;
    margin-top:30px;
}
.animat{
  animation:mymove 5s infinite;
  -webkit-animation:mymove 5s infinite; /*Safari and Chrome*/
  animation-direction:alternate;/*轮流反向播放动画。*/
  animation-timing-function: ease-in-out; /*动画的速度曲线*/
  }
  @keyframes mymove
  {
    0%{
      transform: scale(1);
    }
    25%{
      transform: scale(1.2);
    }
    50%{
      transform: scale(1);
    }
    75%{
      transform: scale(1.2);
    }
  }
.button {
  display: block;
  margin: 10px 0;
  padding: 10px;
  width: 100%;
  height: 100%;
  font-size: 20px;
  color: red;
}
</style>
