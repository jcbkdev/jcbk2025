<script setup lang="ts">
import Hand from './icons/Hand.vue'
</script>

<template>
  <span class="handwave">
    <Hand></Hand>
  </span>
</template>

<style scoped>
.handwave {
  display: inline-block;
  transform-origin: center;
  animation: wave 0.3s infinite alternate ease-in-out;
  margin: 0 6px;
}

@keyframes wave {
  0% {
    transform: rotate(0deg) translate(-3px, 2px);
  }
  100% {
    transform: rotate(17deg) translate(-3px, 2px);
  }
}
</style>
