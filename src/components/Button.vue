<script setup lang="ts">
withDefaults(defineProps<{ onClick?: () => void; fill?: boolean }>(), {
  onClick: () => {},
  fill: false,
})
</script>

<template>
  <button @click="onClick" class="btn" :class="{ filled: fill }">
    <span><slot></slot></span>
    <div class="btn-gradient-bg"></div>
  </button>
</template>

<style scoped>
.btn {
  --animation-speed: 0.2s;
  --animation-ease: ease-out;

  position: relative;
  color: var(--color-text);
  border: 1px solid #ffffff33;
  border-radius: 8px;
  padding: 12px 24px;
  font-family: var(--font-main);
  font-size: 16px;
  font-weight: 700;
  background: var(--grad-bg-10);
  text-shadow: 0px 0px 0px white;
  overflow: hidden;

  cursor: pointer;

  transition:
    border-color var(--animation-speed) var(--animation-ease),
    text-shadow var(--animation-speed) var(--animation-ease);
}

.btn.filled {
  background-color: var(--color-bg);
}

.btn:hover {
  border-color: #ffffffb3;
  text-shadow: 0px 0px 6px white;
}

.btn-gradient-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;

  z-index: -1;

  background: var(--grad-bg-100);
  opacity: 0.1;
  transition: opacity var(--animation-speed) var(--animation-ease);
}

.btn:hover .btn-gradient-bg {
  opacity: 0.3;
}

.btn:disabled {
  cursor: not-allowed;
}
</style>
