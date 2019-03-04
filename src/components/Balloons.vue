<template lang="html">
  <div class="all-balloons">
    <Balloon v-for="balloon in number"></Balloon>
  </div>
</template>

<script>
import Balloon from './Balloon.vue'
export default {
  components: {
    Balloon
  },
  data() {
    return {
      number: 50,
    }
  },
}
</script>

<style lang="css" scoped>
  .all-balloons {
    position: fixed;
    height: 100vh;
    width: 100vw;
    top: 0;
    left: 0;
    overflow: hidden;
  }
</style>
