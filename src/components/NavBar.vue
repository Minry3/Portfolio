<template>
  <header class="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="nav-container">
      <a href="#" class="logo" @click.prevent="scrollToSection('#top')">
        NC<span class="dot">.</span>
      </a>

      <nav class="desktop-nav">
        <a href="#about" class="nav-link" @click.prevent="scrollToSection('#about')">À propos</a>
        <a href="#skills" class="nav-link" @click.prevent="scrollToSection('#skills')">Compétences</a>
        <a href="#education" class="nav-link" @click.prevent="scrollToSection('#education')">Formation</a>
        <a href="#experience" class="nav-link" @click.prevent="scrollToSection('#experience')">Expérience</a>
        <a href="#projects" class="nav-link" @click.prevent="scrollToSection('#projects')">Projets</a>
        <a href="#veille" class="nav-link" @click.prevent="scrollToSection('#veille')">Veille Technologique</a>
      </nav>

      <button class="mobile-toggle" @click="toggleMenu" aria-label="Menu">
        <span class="bar" :class="{ 'open-top': isMenuOpen }"></span>
        <span class="bar" :class="{ 'open-mid': isMenuOpen }"></span>
        <span class="bar" :class="{ 'open-bottom': isMenuOpen }"></span>
      </button>
    </div>

    <div class="mobile-menu" :class="{ 'is-open': isMenuOpen }">
      <nav class="mobile-nav">
        <a href="#about" class="mobile-link" @click.prevent="scrollToSection('#about')">À propos</a>
        <a href="#skills" class="mobile-link" @click.prevent="scrollToSection('#skills')">Compétences</a>
        <a href="#education" class="mobile-link" @click.prevent="scrollToSection('#education')">Formation</a>
        <a href="#experience" class="mobile-link" @click.prevent="scrollToSection('#experience')">Expérience</a>
        <a href="#projects" class="mobile-link" @click.prevent="scrollToSection('#projects')">Projets</a>
        <a href="#veille" class="mobile-link" @click.prevent="scrollToSection('#veille')">Veille Technologique</a>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isMenuOpen = ref(false);
const isScrolled = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  if (isMenuOpen.value) {
    document.body.style.overflow = 'hidden';
  } else {
    document.body.style.overflow = '';
  }
};

const scrollToSection = (sectionId) => {
  isMenuOpen.value = false;
  document.body.style.overflow = '';

  if (sectionId === '#top') {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  } else {
    const element = document.querySelector(sectionId);
    if (element) {
      const navbarHeight = document.querySelector('.navbar').offsetHeight;
      
      const elementPosition = element.getBoundingClientRect().top + window.scrollY;
      
      const pixelsAjustement = 60; 
      
      window.scrollTo({
        top: elementPosition - navbarHeight + pixelsAjustement,
        behavior: 'smooth'
      });
    }
  }
};

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  transition: all 0.3s ease;
  padding: 1.5rem 0;
}

.navbar.scrolled {
  padding: 1rem 0;
  background-color: rgba(248, 244, 230, 0.9); 
  backdrop-filter: blur(10px); 
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.8rem;
  font-weight: 800;
  color: var(--text-blue, #1A365D);
  text-decoration: none;
  font-family: 'Playfair Display', 'Georgia', serif;
  letter-spacing: -0.5px;
  position: relative;
  z-index: 1001; 
}

.dot {
  color: var(--accent-blue, #1E40AF);
}

.desktop-nav {
  display: flex;
  gap: 2.5rem;
}

.nav-link {
  color: var(--text-blue, #1A365D);
  text-decoration: none;
  font-size: 1rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  position: relative;
  transition: color 0.3s ease;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--accent-blue, #1E40AF);
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: var(--accent-blue, #1E40AF);
}

.nav-link:hover::after {
  width: 100%;
}

.mobile-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 20px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1001; 
}

.bar {
  width: 100%;
  height: 2.5px;
  background-color: var(--text-blue, #1A365D);
  border-radius: 5px;
  transition: all 0.3s ease;
}

.open-top {
  transform: translateY(8.5px) rotate(45deg);
}
.open-mid {
  opacity: 0;
}
.open-bottom {
  transform: translateY(-8.5px) rotate(-45deg);
}

.mobile-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: var(--bg-beige, #f8f4e6);
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  visibility: hidden;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  z-index: 1000;
}

.mobile-menu.is-open {
  opacity: 1;
  visibility: visible;
}

.mobile-nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem; 
}

.mobile-link {
  font-size: 1.4rem; 
  font-weight: 800;
  color: var(--text-blue, #1A365D);
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 2px;
  text-align: center;
  transition: color 0.3s ease;
}

.mobile-link:hover {
  color: var(--accent-blue, #1E40AF);
}

@media (max-width: 900px) {
  .desktop-nav {
    display: none;
  }
  
  .mobile-toggle {
    display: flex;
  }

  .nav-container {
    padding: 0 20px;
  }
}
</style>