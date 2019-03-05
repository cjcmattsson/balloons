<template lang="html">
  <div class="all-balloons">
    <div class="close" @click="close">x</div>
    <Balloon v-for="balloon in number"></Balloon>
    <div class="message-wrapper">
      <Message></Message>
    </div>
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
    }
  },
  methods: {
    close() {
      console.log("HERROIEJ")
      document.querySelector('.all-balloons').style.display = "none";
    }
  }
}
</script>

<style lang="css" scoped>
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
