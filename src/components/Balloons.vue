<template lang="html">
  <div class="all-balloons">
    <div class="close" @click="close">x</div>
    <Balloon v-for="balloon in number" v-bind:ribbonCut="ribbonCut"></Balloon>
    <img v-if="removeBanner" src="./banner.gif" alt="">
    <img v-if="!cutBanner" src="./banner.png" alt="" @click="cutRibbon">
    <!-- <div class="message-wrapper" @click="cutRibbon">
      <Message></Message>
    </div> -->
  </div>
</template>

<script>
import Balloon from './Balloon.vue'
import Message from './Message.vue'
export default {
  components: {
    Balloon,
    Message
  },
  data() {
    return {
      number: 50,
      ribbonCut: false,
      cutBanner: false,
      removeBanner: false
    }
  },
  methods: {
    close() {
      document.querySelector('.all-balloons').style.display = "none";
    },
    cutRibbon() {
      this.ribbonCut = true;
      this.removeBanner = true;
      this.cutBanner = true;
      setTimeout(() => {
        this.removeBanner = false;
      }, 1000)
    }
  }
}
</script>

<style lang="css" scoped>
img {
  position: fixed;
  top: 50%;
  left: 50%;
  /* bring your own prefixes */
  transform: translate(-50%, -50%);
  width: auto;
  height: auto;
}
  .message-wrapper {
    position: absolute;
    text-align: left;
    position: fixed;
    top: 50%;
    left: 50%;
    margin-left:-145px;
    margin-top:-145px;
    z-index: 1000;
  }
  .all-balloons {
    overflow: hidden;
    background-color: rgba(247, 187, 205, 0.2);
    position: fixed;
    height: 100vh;
    width: 100vw;
    top: 0;
    left: 0;
    overflow: hidden;
  }
  .close {
    line-height: 1;
    font-weight: 400;
    z-index: 1000;
    margin: 0;
    position: absolute;
    right: 15px;
    top: 12px;
    font-size: 40px;
  }
</style>
