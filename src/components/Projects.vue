<template>
    <section id="projects" class="projects-section">
        <div class="projects-container">
            <div class="section-header">
                <p class="eyebrow">Portfolio</p>
                <h2 class="section-title">Mes Projets</h2>
            </div>

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
                            <a :href="project.github" target="_blank" class="btn-primary" @click.stop>Voir sur GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'; 

const openProject = ref(null);

function toggleProject(title) {
    openProject.value = openProject.value === title ? null : title;
}

const projects = [
    { 
        title: "Application de Gestion", 
        year: "2024",
        details: "Développement d'une interface complexe avec une architecture robuste pour la gestion de données en temps réel.",
        tags: ["React", "API"],
        image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Image_created_with_a_mobile_phone.png/1920px-Image_created_with_a_mobile_phone.png", 
        github: "#" 
    },
    { 
        title: "Site Vitrine E-commerce", 
        year: "2023",
        details: "Refonte totale d'une boutique en ligne avec un focus sur l'UX, la performance et le design responsive.",
        tags: ["JavaScript", "Tailwind"],
        image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Image_created_with_a_mobile_phone.png/1920px-Image_created_with_a_mobile_phone.png", 
        github: "#" 
    }
];
</script>

<style scoped>
.projects-section { padding: 8rem 2rem; }
.projects-container { max-width: 1100px; margin: 0 auto; }

.section-header { text-align: center; margin-bottom: 5rem; }

.section-title { 
    font-size: 3rem; 
    color: var(--text-blue); 
    margin: 0; 
    font-weight: 800; 
    position: relative;
    display: inline-block;
    padding-bottom: 1rem;
}

.section-title::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 70px;
    height: 5px;
    background: var(--accent-blue);
    border-radius: 3px;
}

.eyebrow { color: var(--accent-blue); text-transform: uppercase; font-weight: 700; letter-spacing: 0.15em; margin-bottom: 1rem; }

.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 3rem;
    align-items: start;
}

.project-card {
    background: transparent; 
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
</style>