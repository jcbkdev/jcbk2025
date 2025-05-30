<script setup lang="ts">
import { ref } from 'vue'
import ProjectPreview from './ProjectPreview.vue'
import ProjectIndicator from './ProjectIndicator.vue'

defineProps<{
  name: string
  img: string
  url: string
  github?: string
  isActive?: boolean
}>()

const showModal = ref(false)

let isHovered = ref(false)
</script>

<template>
  <div @mouseover="isHovered = true" @mouseout="isHovered = false" class="project-card-wrapper">
    <ProjectIndicator v-if="isActive" :is-hovered="isHovered" />
    <div class="project-card" @click="showModal = true">
      <div
        class="project-img"
        :class="img ? '' : 'placeholder'"
        v-bind:data-image="img ?? null"
        :style="img && `--bg-url: url('${img}')`"
      ></div>
      <div class="project-details">
        <h3>{{ name ?? 'Project Name' }}</h3>
      </div>
      <div class="project-bg"></div>
    </div>
  </div>
  <ProjectPreview v-if="showModal" :url="url" :github="github" @close="showModal = false" />
</template>

<style scoped>
.project-card-wrapper {
  position: relative;
  width: max-content;
  height: max-content;
}

.project-card {
  --animation-speed: 0.2s;
  --animation-ease: ease-out;

  display: flex;
  flex-direction: column;

  position: relative;

  width: 240px;
  max-width: 240px;
  height: 360px;
  max-height: 360px;

  border: 1px solid #ffffff33;
  border-radius: 8px;
  overflow: hidden;

  cursor: pointer;

  transition: border-color var(--animation-speed) var(--animation-ease);
}

.project-card:hover {
  border-color: #ffffffb3;
}

.project-img {
  height: 100%;
  width: 100%;
}

.project-img[data-image] {
  background: var(--bg-url);
  opacity: 0.4;
  background-position: center;
  background-size: cover;

  transition: opacity var(--animation-speed) var(--animation-ease);
}

.placeholder {
  background: 5%/5% url('/placeholder.png');
  opacity: 0.1;
}

.project-details {
  display: flex;
  align-items: center;
  justify-content: center;
  border-top: 1px solid #ffffff33;

  height: 48px;
  width: 100%;

  transition:
    border-color var(--animation-speed) var(--animation-ease),
    text-shadow var(--animation-speed) var(--animation-ease);
}

.project-bg {
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

.project-card:hover .project-bg {
  opacity: 0.3;
}

.project-card:hover .project-details {
  border-color: #ffffffb3;
  text-shadow: 0px 0px 6px white;
}

.project-card:hover .project-img[data-image] {
  opacity: 0.7;
}
</style>
