<template>
  <div class="dots-grad">
    <div class="dots-bg"></div>
  </div>
</template>

<style scoped>
.dots-grad {
  position: fixed;
  height: 100vh;
  width: 100vw;
  top: 0;
  left: 0;
  z-index: -9;

  overflow: hidden;

  mask-image: radial-gradient(var(--color-bg), var(--color-bg-0) 70%);
}

.dots-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: calc(100% + 128px);
  height: calc(100% + 128px);
  background: url('/dot.png') repeat;
  opacity: 0.6;
  background-size: 2rem;
  animation: move 2s linear infinite;
}

@keyframes move {
  0% {
    transform: translate(-128px, -128px);
  }

  100% {
    transform: translate(0, 0);
  }
}
</style>
