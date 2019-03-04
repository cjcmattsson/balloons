<template lang="html">
  <div class="balloon-wrapper"
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
  name: "Balloon",
  data() {
    return {
      colors: ["#DCEED1", "#A18276", "#E80C7A", "#FF530D", "#FF0DFF", "#00EAFF", "#A8FF0D", "#FFF200"],
      chosenColor: false,
      randSpeed: false,
      randLeft: false,
      randDelay: false
    }
  },
  mounted() {
    this.randSpeed = Math.random() * 6 + 1;
    this.randDelay = Math.random() * 3 + 1;
    this.randLeft = Math.floor(Math.random() * 87) + 0;
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
  animation-name: moveBalloon;
  animation-fill-mode: forwards;
  z-index: 1000;
}
@keyframes moveBalloon {
  from {top: 100vh;}
  to {top: -50vh;}
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
    .balloon:after {
      display: inline-block;
      top: 140px;
      position: absolute;
      height: 150px;
      width: 1px;
      margin: 0 auto;
      content: "";
      background: rgba(0, 0, 0, 0.2);
    z-index: -120}
</style>
