<script setup lang="ts">
import ProjectCard from '../components/ProjectCard.vue'
</script>

<template>
  <section id="projects">
    <h2 class="projects-title">Projects</h2>
    <div class="projects-container">
      <ProjectCard
        name="Duskvale"
        img="/duskvale.png"
        url="https://duskvale.com"
        github="https://github.com/jcbkdev/duskvale-blog"
        :is-active="true"
      />
      <ProjectCard
        name="Freelancing Website"
        img="/img.png"
        url="https://dev.jcbk.pl"
        github="https://github.com/jcbkdev/jcbkdev-freelance"
      />
      <ProjectCard
        name="SaveCash"
        img="/savecash.png"
        url="https://savecash.jcbk.pl"
        github="https://github.com/jcbkdev/savecash"
      />
      <ProjectCard
        name="GameDeals"
        img="/gamedeals.png"
        url="https://gamedeals.jcbk.pl"
        github="https://github.com/jcbkdev/gamedeals-jcbk"
      />
    </div>
  </section>
</template>

<style scoped>
#projects {
  display: flex;
  flex-direction: column;
  align-items: center;
  box-sizing: border-box;
}

.projects-title {
  font-size: var(--font-section-title-size);
  font-weight: var(--font-section-title-weight);
  margin: 0;
  margin-bottom: 24px;
}

.projects-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 24px;
}
</style>
