<template>
    <section id="projects" class="projects-section">
        <div class="projects-container">
            <SectionHeader title="Mes Projets" />

            <div class="projects-grid">
                <div 
                    class="project-card" 
                    v-for="project in projects" 
                    :key="project.title"
                    :class="{ 'is-open': openProject === project.title }"
                    @click="toggleProject(project.title)"
                >
                    <img :src="project.image" :alt="project.title" class="preview-image">

                    <div class="card-preview">
                        <span class="year">{{ project.year }}</span>
                        <h3>{{ project.title }}</h3>
                        <div class="tags-container">
                            <span class="skill-tag" v-for="tag in project.tags" :key="tag">{{ tag }}</span>
                        </div>
                        <button class="toggle-btn" @click.stop="toggleProject(project.title)">
                            {{ openProject === project.title ? 'Voir moins' : 'Voir plus de détails' }}
                        </button>
                    </div>

                    <div class="card-details">
                        <div class="card-details-inner">
                            <p>{{ project.details }}</p>
                            <div class="btn-wrapper">
                                <a :href="project.github" target="_blank" class="btn-primary" @click.stop>
                                    <img src="../assets/logos/github-white-icon.webp" alt="Logo GitHub" class="btn-icon">
                                    Voir sur GitHub
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'; 
import SectionHeader from './SectionHeader.vue';
import imgEchec from '../assets/Projets/jeu-echecs-java.png';

const openProject = ref(null);

function toggleProject(title) {
    openProject.value = openProject.value === title ? null : title;
}

const projects = [
    { 
        title: "Jeu d'échecs", 
        year: "2025",
        details: `Création d’un jeu d’échecs en java, dans le cadre de mon BUT Informatique. Celui-ci peut être lancé à partir d’un terminal comme celui de Linux.

                Il s’agit d’une partie simplifiée, permettant de détecter les cas de pat ainsi que d’échec et mat.

                La programmation du jeu a été réalisée de façon collaborative à l’aide de Git. L’objectif de ce projet était notamment de comprendre et de maîtriser la programmation orientée objet dans un contexte concret.`,
        tags: ["Java", "Git"],
        image: imgEchec, 
        github: "https://github.com/Minry3/Jeu-echec-java" 
    },
    { 
        title: "MediaTek86", 
        year: "2024",
        details: "[ajouter description]",
        tags: ["C#"],
        image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Image_created_with_a_mobile_phone.png/1920px-Image_created_with_a_mobile_phone.png", 
        github: "https://github.com/Minry3/MediaTek86" 
    },
    { 
        title: "OWLearning", 
        year: "2025-2026",
        details: "[ajouter description]",
        tags: ["SpringBoot", "Vue.js", "SQL"],
        image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Image_created_with_a_mobile_phone.png/1920px-Image_created_with_a_mobile_phone.png", 
        github: "https://github.com/OWLearning-Project/OWLearning" 
    },
    { 
        title: "On Sort ? (Projet en cours)", 
        year: "2026",
        details: "[ajouter description]",
        tags: ["Vue.js"],
        image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Image_created_with_a_mobile_phone.png/1920px-Image_created_with_a_mobile_phone.png", 
        github: "#" 
    },
];
</script>

<style scoped>
.projects-section { padding: 8rem 2rem; }
.projects-container { max-width: 1100px; margin: 0 auto; }

.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 450px), 1fr));
    gap: 3rem;
    align-items: start;
}

.project-card {
    background-color: rgba(255, 255, 255, 0.6); ; 
    border: 2px solid var(--accent-blue);
    border-radius: 20px;
    overflow: hidden;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    box-shadow: 8px 8px 0px rgba(43, 108, 176, 0.1); 
}

.project-card:hover {
    transform: translateY(-8px);
    box-shadow: 12px 12px 0px rgba(43, 108, 176, 0.2);
}

.preview-image {
    width: 100%;
    height: 280px;
    object-fit: cover;
    display: block;
}

.card-preview {
    padding: 2rem;
}

.year {
    font-weight: 800;
    color: var(--accent-blue);
    font-size: 1rem;
}

.project-card h3 {
    margin: 0.3rem 0 1rem 0;
    font-size: 1.6rem;
    color: var(--text-blue);
}

.tags-container { display: flex; gap: 0.6rem; flex-wrap: wrap; margin-bottom: 1.5rem; }
.skill-tag { 
    font-size: 0.85rem; 
    padding: 0.4rem 0.8rem; 
    border: 1px solid var(--accent-blue);
    border-radius: 6px;
    color: var(--text-blue);
    font-weight: 600;
}

.toggle-btn {
    background: none;
    border: none;
    color: var(--accent-blue);
    font-weight: 700;
    font-size: 0.95rem;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
}

.card-details {
    display: grid;
    grid-template-rows: 0fr;
    transition: grid-template-rows 0.35s cubic-bezier(0.4, 0, 0.2, 1);
}

.project-card.is-open .card-details {
    grid-template-rows: 1fr;
}

.card-details-inner {
    overflow: hidden;
}

.card-details-inner p {
    color: var(--text-blue);
    opacity: 0.85;
    line-height: 1.7;
    padding: 0 2rem;
    margin: 0 0 1.5rem 0;
}

.card-details .btn-primary {
    margin: 0 2rem 2rem 2rem;
    display: inline-block;
}

.card-details-inner p {
    white-space: pre-line;
    text-align: justify;
}

.btn-wrapper {
  display: flex;
  justify-content: center; 
  width: 100%;
  margin-top: 25px; 
}

.btn-primary {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px; 
  padding: 12px 20px;
  background-color: var(--accent-blue);
  color: white;
  border-radius: 50px;
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: bold;
  transition: all 0.3s ease;
  line-height: 1;
}

.btn-primary:hover {
  background-color: var(--text-blue);
  transform: translateY(-2px);
}

.btn-icon {
  width: 20px;  
  height: 20px;
  object-fit: contain;
  transform: translateY(-1px); 
  margin-bottom: -4px;
}
</style>