<script setup lang="ts">
import HandWave from '../components/HandWave.vue'
import Button from '../components/Button.vue'
import AstroImage from '../components/AstroImage.vue'
</script>

<template>
  <section id="hero">
    <div class="col-left">
      <h1 class="hero-title">Hi!<HandWave />I'm Jakub Konieczny</h1>
      <p class="hero-desc">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nesciunt et quae incidunt quam
        corporis! Expedita distinctio modi numquam voluptatum voluptatibus sint dignissimos iste,
        excepturi animi ullam exercitationem voluptatem dolor corrupti!
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
  margin-bottom: 24px;
}

.hero-desc {
  margin: 0;
  margin-bottom: 24px;
}
</style>
