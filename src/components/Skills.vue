<template>
    <section id="skills" class="skills-section">
        <div class="skills-container">
            <SectionHeader title="Mes Compétences" />

            <div class="skills-grid">
                
                <div class="skill-card">
                    <div class="card-header">
                        <h3>Front-End</h3>
                    </div>
                    <div class="tags-container">
                        <span class="skill-tag">
                            <img src="../assets/logos/html.png" alt="HTML" class="skill-icon"> HTML
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/css.png" alt="CSS" class="skill-icon"> CSS
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/js.png" alt="JavaScript" class="skill-icon"> JavaScript
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/vue-js.png" alt="Vue.js" class="skill-icon"> Vue.js
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/mudblazor.png" alt="MudBlazor" class="skill-icon"> MudBlazor
                        </span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="card-header">
                        <h3>Back-End</h3>
                    </div>
                    <div class="tags-container">
                        <span class="skill-tag">
                            <img src="../assets/logos/c-sharp.png" alt="C#" class="skill-icon">C#
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/java.webp" alt="Java" class="skill-icon">Java
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/python.png" alt="Python" class="skill-icon">Python
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/node-js.png" alt="Node.js" class="skill-icon">Node.js
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/spring.png" alt="SpringBoot" class="skill-icon">SpringBoot
                        </span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="card-header">
                        <h3>Base de données & Architecture</h3>
                    </div>
                    <div class="tags-container">
                        <span class="skill-tag">
                            <img src="../assets/logos/postgresql.png" alt="PostgreSQL" class="skill-icon">PostgreSQL
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/sql.png" alt="SQL" class="skill-icon">SQL
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/docker.png" alt="Docker" class="skill-icon">Docker
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/linux.png" alt="Linux" class="skill-icon">Linux
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/windows-11.png" alt="Windows" class="skill-icon">Windows
                        </span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="card-header">
                        <h3>Outils & Logiciels</h3>
                    </div>
                    <div class="tags-container">
                        <span class="skill-tag">
                            <img src="../assets/logos/git.png" alt="Git" class="skill-icon">Git
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/vscode.png" alt="VS Code" class="skill-icon">VS Code
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/visual-studio.png" alt="Visual Studio" class="skill-icon">Visual Studio
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/android-studio-icon.png" alt="Android Studio" class="skill-icon">Android Studio
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/canva-icon.png" alt="Canva" class="skill-icon">Canva
                        </span>
                        <span class="skill-tag">
                            <img src="../assets/logos/microsoft-office.png" alt="Pack Office" class="skill-icon">Pack Office
                        </span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="card-header">
                        <h3>Soft Skills</h3>
                    </div>
                    <div class="tags-container">
                        <span class="skill-tag">Rigoureuse</span>
                        <span class="skill-tag">Curieuse</span>
                        <span class="skill-tag">Autonome</span>
                        <span class="skill-tag">Organisée</span>
                        <span class="skill-tag">À l’écoute</span>
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
.skills-section {
    padding: 6rem 2rem;
}

.skills-container {
    max-width: 1200px;
    margin: 0 auto;
}

.skills-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2.5rem; 
}

.skill-card {
    flex: 1 1 300px;
    max-width: 450px;
    background-color: rgba(255, 255, 255, 0.6); 
    border-radius: 16px;
    padding: 2rem;
    border: 2px solid var(--accent-blue);
    box-shadow: 6px 6px 0px rgba(43, 108, 176, 0.15); 
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column;
}

.skill-card:hover {
    transform: translate(-4px, -4px);
    box-shadow: 10px 10px 0px rgba(43, 108, 176, 0.25);
}

.card-header {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    margin-bottom: 1rem;
}

.skill-card h3 {
    margin: 0;
    font-size: 1.35rem;
    color: var(--text-blue);
    font-weight: 800;
}

.card-desc {
    color: var(--text-blue);
    opacity: 0.8;
    font-size: 0.95rem;
    line-height: 1.5;
    margin: 0 0 1.5rem 0;
}

.tags-container {
    display: flex;
    flex-wrap: wrap; 
    gap: 0.75rem;
    margin-top: auto; 
}

.skill-tag {
    background-color: transparent;
    border: 1px solid var(--accent-blue);
    color: var(--text-blue);
    padding: 0.4rem 0.8rem;
    border-radius: 8px; 
    font-size: 0.85rem;
    font-weight: 600;
    transition: all 0.2s ease;
    
    display: inline-flex;
    align-items: center;
    gap: 0.4rem; 
}

.skill-tag:hover {
    background-color: var(--accent-blue);
    color: #ffffff;
    cursor: default;
}

.skill-icon {
    width: 22px;
    height: 22px;
    object-fit: contain; 
}
</style>