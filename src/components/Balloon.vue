<template lang="html">
  <div v-bind:class="[this.ribbonCut ? 'animate-balloon' : '', 'balloon-wrapper']"
  @click="explode"
  v-bind:style="{
    left: randLeft ? randLeft+'vw' : '',
    animationDuration: randSpeed ? randSpeed+'s' : '',
    animationDelay: randDelay ? randDelay+'s' : ''}">
    <div class="balloon" :style="{backgroundColor: chosenColor, color: chosenColor}"></div>
  </div>
</template>

<script>
export default {
  props: ['ribbonCut'],
  name: "Balloon",
  data() {
    return {
      colors: ["#343735", "#E6E7E8", "#EF5D52", "#008DA8", "#008DA8", "#54B848", "#54B848", ],
      chosenColor: false,
      randSpeed: false,
      randLeft: false,
      test: false,
      randDelay: false
    }
  },
  mounted() {
    this.randSpeed = Math.random() * 6 + 1;
    this.randDelay = Math.random() * 2 + 0;
    this.randLeft = Math.floor(Math.random() * 95) + (-5);
    this.chosenColor = this.colors[Math.floor(Math.random() * this.colors.length)];
  },
  methods : {
    explode() {
      console.log("PANG");
    }
  }
}
</script>

<style lang="css" scoped>
.balloon-wrapper {
  top: 100vh;
  margin: 0 auto;
  height: auto;
  width: auto;
  position: absolute;
  /* animation-iteration-count: infinite; */
  z-index: 1000;
}
.animate-balloon {
  animation-name: moveBalloon;
  animation-fill-mode: forwards;
}
@keyframes moveBalloon {
  0% {
    top: 100vh;
  }
  100% {
    top: -50vh;
  }
}
.balloon {
    display: inline-block;
    width: 120px;
    height: 145px;
    background: #85d6ff;
    border-radius: 80%;
    position: relative;
    -webkit-box-shadow: inset -10px -10px 0 rgba(0, 0, 0, 0.07);
    box-shadow: inset -10px -10px 0 rgba(0, 0, 0, 0.07);
    margin: 20px 30px;}
    .balloon:before {
      content: "▲";
      font-size: 20px;
      color: inherit;
      display: block;
      text-align: center;
      width: 100%;
      position: absolute;
      bottom: -12px;
      z-index: -100; }
    @media (max-width: 946px) {
      .balloon {
        height: 100px;
        width: 85px;
        margin-left: 0;
      }

      .balloon:after {
        display: none;
      }
    }
</style>
