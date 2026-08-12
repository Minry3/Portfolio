<template>
  <div class="app-container">
    <NavBar />
    <HeroProfile />
    <AboutMe />
    <Skills />
    <Formation /> 
    <Experience />
    <Projects />
    <Veille />
    <Footer />
  </div>
</template>

<script setup>
import HeroProfile from './components/ProfilSection.vue'
import AboutMe from './components/AboutMe.vue'
import Skills from './components/Skills.vue';
import Formation from './components/Formation.vue';
import Experience from './components/Experience.vue';
import Projects from './components/Projects.vue';
import NavBar from './components/NavBar.vue';
import Veille from './components/Veille.vue';
import Footer from './components/Footer.vue';
</script>

<style>
:root {
  --bg-beige: #F8F4E6;
  --text-blue: #1A365D; 
  --accent-blue: #2B6CB0;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: var(--bg-beige);
  color: var(--text-blue);
  font-family: 'Inter', system-ui, sans-serif; 
}
</style>