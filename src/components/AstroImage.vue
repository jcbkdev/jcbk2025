<script setup lang="ts">
import Git from './icons/Git.vue'
import React from './icons/React.vue'
import Figma from './icons/Figma.vue'
import Css from './icons/Css.vue'
import Typescript from './icons/Typescript.vue'
import Javascript from './icons/Javascript.vue'
</script>

<template>
  <div class="astro-container">
    <div class="spinner">
      <Figma />
      <React />
      <Typescript />
      <Git />
      <Css />
      <Javascript />
    </div>
    <img class="photo" src="/me.png" alt="" />
  </div>
</template>

<style scoped>
.astro-container {
  position: relative;
  width: 420px;
  height: 480px;
}

.spinner {
  --animation-speed: 3s;

  position: absolute;
  top: 30%;
  left: 16%;
  width: 62%;

  display: flex;
  justify-content: space-between;
}

.spinner > :nth-child(n) {
  position: absolute;
  width: 520px;
  offset-rotate: 0deg;
  offset-path: polygon(0% 0%, 100% 0%, 0% 0%, 0% 0%);
}

.spinner > :nth-child(1) {
  animation: spin var(--animation-speed) infinite linear;
}

.spinner > :nth-child(2) {
  animation: spin var(--animation-speed) calc(var(--animation-speed) / 6 * -1) infinite linear;
}

.spinner > :nth-child(3) {
  animation: spin var(--animation-speed) calc(var(--animation-speed) / 6 * -2) infinite linear;
}

.spinner > :nth-child(4) {
  animation: spin var(--animation-speed) calc(var(--animation-speed) / 6 * -3) infinite linear;
}

.spinner > :nth-child(5) {
  animation: spin var(--animation-speed) calc(var(--animation-speed) / 6 * -4) infinite linear;
}

.spinner > :nth-child(6) {
  animation: spin var(--animation-speed) calc(var(--animation-speed) / 6 * -5) infinite linear;
}

.photo {
  width: 100%;
}

@keyframes spin {
  from {
    filter: grayscale(0.5) blur(2px);
    transform: scale(0.8);
    z-index: 1;
  }
  10% {
    filter: grayscale(0) blur(0);
  }
  25% {
    transform: scale(1);
    z-index: 2;
  }
  36% {
    filter: grayscale(0) blur(0);
    transform: scale(0.8);
    z-index: 0;
  }
  50% {
    filter: grayscale(0.7) blur(2px);
    transform: scale(0.6);
    z-index: -1;
  }
  75% {
    transform: scale(0.4);
  }
  83% {
    filter: grayscale(0.7) blur(2px);
    transform: scale(0.6);
    z-index: -1;
  }
  to {
    filter: grayscale(0.7) blur(2px);
    z-index: 0;
    transform: scale(0.8);
    offset-distance: 100%;
  }
}
</style>
