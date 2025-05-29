<script setup lang="ts">
import Landing from './components/Landing.vue'
import Hero from './sections/Hero.vue'
import DotsBg from './components/DotsBg.vue'
import Projects from './sections/Projects.vue'
import Contact from './sections/Contact.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <Landing />
  <main>
    <Hero />
    <Projects />
    <Contact />
  </main>
  <Footer></Footer>
  <DotsBg />
</template>
