<template>
  <div/>
</template>

<style scoped>
div {
  background-image: url(../images/bender.png);
  width: 100px;
  height: 70%;
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
  margin: 0 auto;
  animation: animate 1s infinite;
}

@keyframes animate {
  from {
    transform-origin: center;
    transform: rotate(0deg);
  }

  to {
    transform-origin: center;
    transform: rotate(360deg);
  }
}
</style>