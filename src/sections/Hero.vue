<script setup lang="ts">
import HandWave from '../components/HandWave.vue'
import Button from '../components/Button.vue'
import AstroImage from '../components/AstroImage.vue'
</script>

<template>
  <section id="hero">
    <div class="col-left">
      <h1 class="hero-title">Hi!<HandWave />I'm Jakub Konieczny</h1>
      <h2 class="hero-label">Frontend Developer</h2>
      <p class="hero-desc">
        I build fast, responsive web apps with React and TypeScript focused on a clean UI and great
        performance on multiple platforms. Lately, I've been working on <b><i>Duskvale</i></b> which
        is a browser-based MMO with no pay-to-win, just solid gameplay. I enjoy building things that
        feel good and work everywhere! I am always looking for ways to challenge myself and try out
        new tools.
      </p>

      <Button
        :onClick="
          () => {
            scrollToContact()
          }
        "
        >Contact</Button
      >
    </div>
    <div class="col-right">
      <AstroImage></AstroImage>
    </div>
  </section>
</template>

<script lang="ts">
function scrollToContact() {
  const contactSection = document.getElementById('contact')
  if (!contactSection) return console.error("Couldn't find a contact section")

  contactSection.scrollIntoView({ behavior: 'smooth' })
  return console.log('scrolling')
}
</script>

<style scoped>
#hero {
  display: flex;
  align-items: center;
  box-sizing: border-box;
  justify-content: space-around;
  width: 100%;
  max-width: 1440px;
}

.col-left {
  width: min-content;
}

.hero-title {
  width: max-content;
  font-size: var(--font-section-title-size);
  font-weight: var(--font-section-title-weight);
  margin: 0;
  margin-bottom: -16px;
}

.hero-label {
  margin: 0;
  margin-bottom: 16px;
}

.hero-desc {
  margin: 0;
  margin-bottom: 24px;
}
</style>
