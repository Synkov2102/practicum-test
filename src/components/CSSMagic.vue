<template>
  <div class="cube-container">
    <div class="cube">
      <div class="side front">1</div>
      <div class="side back">2</div>
      <div class="side left">3</div>
      <div class="side right">4</div>
      <div class="side top">5</div>
      <div class="side bottom">6</div>
    </div>
  </div>
</template>

<style scoped>
.cube-container {
  perspective: none;
}

.cube {
  width: 50px;
  height: 50px;
  position: relative;
  transform-style: preserve-3d;
  animation: roll 4s infinite linear;
}

.side {
  width: 50px;
  height: 50px;
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  color: white;
}

.front {
  background-color: red;
  transform: translateZ(25px);
}
.back {
  background-color: blue;
  transform: rotateY(180deg) translateZ(25px);
}
.left {
  background-color: green;
  transform: rotateY(-90deg) translateZ(25px);
}
.right {
  background-color: orange;
  transform: rotateY(90deg) translateZ(25px);
}
.top {
  background-color: purple;
  transform: rotateX(90deg) translateZ(25px);
}
.bottom {
  background-color: cyan;
  transform: rotateX(-90deg) translateZ(25px);
}

@keyframes roll {
  0%,
  100% {
    transform: rotateX(0deg) rotateY(0deg);
  }
  25% {
    transform: rotateX(0deg) rotateY(90deg);
  }
  50% {
    transform: rotateX(0deg) rotateY(180deg) rotateZ(90deg);
  }
  75% {
    transform: rotateX(0deg) rotateY(360deg);
  }
}
</style>
