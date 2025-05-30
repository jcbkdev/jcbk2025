<script setup lang="ts">
defineProps<{
  isHovered: boolean
}>()
</script>

<template>
  <div class="project-indicator" :class="{ hovered: isHovered }">
    <span class="project-indicator-text">Active Project</span>
  </div>
</template>

<style scoped>
.project-indicator {
  position: absolute;
  top: -15px;
  right: -15px;

  display: flex;
  align-items: center;
  overflow: hidden;

  width: 29px;
  max-width: max-content;
  padding: 0;
  height: 29px;
  font-size: 16px;
  font-family: 'Host Grotesk';
  background: var(--grad-bg-30);
  background-color: #14ff7e;
  z-index: 1;
  border-radius: 100px;

  transition: 0.5s ease;

  animation: flash 1s infinite ease-out;
}

.project-indicator-text {
  text-wrap: nowrap;
  font-weight: 700;
  user-select: none;
  opacity: 0;
  transition: 0.5s ease-in-out;
}

.project-indicator.hovered {
  max-width: max-content;
  width: 100%;
  padding: 0 12px;
}

.project-indicator.hovered .project-indicator-text {
  opacity: 1;
}

@keyframes flash {
  0% {
    outline: 0px solid #14ff7e;
  }

  50% {
    outline: 6px solid #14ff7e00;
  }

  100% {
    outline: 6px solid #14ff7e00;
  }
}
</style>
