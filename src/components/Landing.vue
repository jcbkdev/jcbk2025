<script setup lang="ts">
import DotsBg from './DotsBg.vue'
</script>

<template>
  <div class="landing">
    <div class="display">
      <span class="display-text">JCBK</span>
      <img class="display-image" src="/logo.svg" alt="-" />
    </div>
    <DotsBg />
  </div>
</template>

<style scoped>
.landing {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 50;
  width: 100vw;
  height: 100vh;
  background-color: var(--color-bg);
  animation: fadeOut 0.5s ease forwards;
  animation-delay: 1s;
}

.display {
  position: relative;
  width: 100%;
  height: 100%;
}
.display-text {
  position: absolute;
  font-size: 64px;
  animation: fontAnim 0.5s linear forwards;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
.display-image {
  position: absolute;
  animation: showAnim 0s forwards linear;
  opacity: 0;
  animation-delay: 0.5s;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

@keyframes fontAnim {
  0% {
    font-family: 'Host Grotesk';
  }
  20% {
    font-family: 'Trebuchet MS';
    font-weight: 700;
  }
  40% {
    font-family: 'Times New Roman', Times, serif;
    font-weight: 400;
  }
  60% {
    font-family:
      'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana,
      sans-serif;
    font-weight: 100;
    font-style: italic;
  }
  80% {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-weight: 900;
  }
  100% {
    display: none;
    font-family: 'Host Grotesk';
  }
}

@keyframes showAnim {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fadeOut {
  from {
    opacity: 1;
    display: unset;
  }
  to {
    opacity: 0;
    display: none;
  }
}
</style>
