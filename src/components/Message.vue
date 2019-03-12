<template lang="html">
    <div href="google.com" class="border">
      <div class="message">
        <h1>Hurra!</h1>
        <h3>Vi öppnar vår 200:e butik! Det firar vi med massa goa priser under mars månad!</h3>
      </div>
    </div>
</template>

<script>
export default {
  methods: {
    
  }
}
</script>

<style lang="css" scoped>
.border {
  text-decoration: none;
  z-index: 1000;
  color: white;
  height: 290px;
  width: 290px;
  border-radius: 50%;
  border: 3px solid black;
  display: flex;
  transform: scale(0);
  align-items: center;
  justify-content: center;
  background-color: white;
  animation-name: spinning;
  animation-duration: 2s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
  animation-timing-function: ease;
  transition: all 0.5s ease;
}
  .message {
    border: 3px solid black;
    height: 275px;
    width: 275px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }

  .border:hover {
    text-decoration: none;
    transform: scale(0)
  }

  h1, h3 {
    text-decoration: none;
    text-align: center;
    text-transform: uppercase;
    max-width: 80%;
  }

  h1 {
    font-weight: 900;
    color: black;
    font-size: 45px;
    margin-bottom: 0;
  }
  h3 {
    margin-top: 0;
    margin-bottom: 20px;
    color: #f7bbcd;
  }
  @keyframes spinning {
    0% {
      transform: scale(0) rotate(0);
    }
    100% {
      transform: scale(1) rotate(10deg);
    }
  }
</style>
