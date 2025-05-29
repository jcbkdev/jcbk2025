<script setup lang="ts">
import Button from './Button.vue'
import Loading from './Loading.vue'
import { defineEmits } from 'vue'

const emit = defineEmits(['close'])

defineProps<{
  url: string
  github: string
}>()

const openInNewTab = (url: string) => {
  window.open(url, '_blank')
}
</script>

<template>
  <div class="preview-bg">
    <div class="preview">
      <iframe :src="url" frameborder="0"></iframe>
      <Loading class="preview-loading" />
      <div class="buttons">
        <Button
          :onClick="
            () => {
              enableScroll()
              emit('close')
            }
          "
          >Close</Button
        >
        <Button :onClick="() => openInNewTab(github)">GitHub</Button>
        <Button
          :onClick="
            () => {
              openInNewTab(url)
              emit('close')
            }
          "
          >Open in a new tab</Button
        >
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  mounted() {
    document.body.style.overflow = 'hidden'
  },
}

function enableScroll() {
  document.body.style.overflow = ''
}
</script>

<style scoped>
.preview-loading {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  transform-origin: top left;
  z-index: 11;
}

.preview-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: var(--color-bg-30);

  display: flex;
  align-items: center;
  justify-content: center;

  overflow: hidden;

  z-index: 10;
}

.preview {
  position: relative;
  width: 80vw;
  height: 80vh;
  background: var(--grad-bg-10) var(--color-bg);
  border: 1px solid #ffffff4d;
  border-radius: 8px;
}

.preview iframe {
  position: relative;
  width: 100%;
  height: 100%;
  border-radius: 8px;
  z-index: 12;
}

.buttons {
  position: absolute;
  bottom: -1.5rem;
  right: 2rem;

  display: flex;
  gap: 12px;
  z-index: 15;
}
</style>
