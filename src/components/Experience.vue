<template>
    <section id="experience" class="experience-section section-full-dark">
        <div class="bg-decorations-wrapper">
            <div class="blob blob-right"></div>
            <div class="blob blob-left"></div>
            <div class="dots-clean"></div>
        </div>

        <div class="experience-container">
            <SectionHeader title="Expérience Professionnelle" />

            <div class="experience-list">
                <div class="experience-card">
                    <div class="card-left">
                        <span class="date-badge">2025 - Présent</span>
                        <h4 class="company">Salvia Développement - Paris</h4>
                    </div>
                    <div class="card-right">
                        <h3>Apprentie R&D - Développeuse FullStack</h3>
                        <p>Développement et maintenance de solutions logicielles, conception d'un outil de gestion interne, revue de code </p>
                        <div class="tags-container">
                            <span class="skill-tag">C#</span>
                            <span class="skill-tag">MudBlazor</span>
                            <span class="skill-tag">Visual Studio</span>
                        </div>
                    </div>
                </div>

                <div class="experience-card">
                    <div class="card-left">
                        <span class="date-badge">Août 2025</span>
                        <h4 class="company">L'Oréal - Levallois-Perret</h4>
                    </div>
                    <div class="card-right">
                        <h3>Job étudiant au sein de l'équipe IT</h3>
                        <p>Analyse de données, préparation de tests utilisateurs, projet de documentation, découverte de la communication en entreprise</p>
                        <div class="tags-container">
                            <span class="skill-tag">PowerPoint</span>
                            <span class="skill-tag">Excel</span>
                            <span class="skill-tag">Travail en équipe</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import SectionHeader from './SectionHeader.vue';
</script>

<style scoped>
.experience-section { 
    padding: 8rem 2rem; 
}

@keyframes morph-alt {
    0%, 100% { border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%; }
    50% { border-radius: 30% 60% 70% 40% / 50% 60% 30% 60%; }
}

.blob {
    position: absolute;
    animation: morph-alt 15s ease-in-out infinite alternate;
}

.blob-right {
    top: 5%; right: -10%;
    width: 550px; height: 550px;
    background: rgba(248, 244, 230, 0.025);
}

.blob-left {
    bottom: -15%; left: -5%;
    width: 450px; height: 450px;
    background: rgba(248, 244, 230, 0.035);
    animation-duration: 20s; 
}

.experience-container { position: relative; z-index: 1; max-width: 900px; margin: 0 auto; }

.experience-card {
    display: grid; grid-template-columns: 240px 1fr; gap: 3rem; padding: 3rem 0;
    border-bottom: 1px solid rgba(248, 244, 230, 0.15);
}

.experience-card:last-child { border-bottom: none; }

.date-badge {
    display: inline-block; font-size: 0.95rem; color: var(--accent-blue); background-color: var(--bg-beige);
    padding: 0.3rem 0.8rem; border-radius: 50px; font-weight: 700; margin-bottom: 0.75rem;
}

.company { color: rgba(248, 244, 230, 0.9); font-size: 1.3rem; font-weight: 700; }
.card-right h3 { margin: 0 0 1.25rem 0; color: var(--bg-beige); font-size: 1.6rem; }
.card-right p { color: var(--bg-beige); opacity: 0.85; line-height: 1.8; font-size: 1.1rem; margin-bottom: 1.5rem; }

.tags-container { display: flex; gap: 0.8rem; flex-wrap: wrap; }
.skill-tag { 
    font-size: 0.9rem; padding: 0.4rem 0.8rem; border: 1px solid rgba(248, 244, 230, 0.4);
    color: var(--bg-beige); background-color: rgba(255, 255, 255, 0.05); border-radius: 6px; font-weight: 600;
}

@media (max-width: 768px) {
    .experience-card { grid-template-columns: 1fr; gap: 1.5rem; }
}
</style>