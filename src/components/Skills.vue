<template>
    <section id="skills" class="skills-section">
        <div class="skills-container">
            <div class="section-header">
                <p class="eyebrow">Mon expertise</p>
                <h2 class="section-title">Mes Compétences</h2>
            </div>

            <div class="skills-grid">
                
                <div class="skill-card">
                    <div class="card-header">
                        <h3>Frontend</h3>
                    </div>
                    <p class="card-desc">Création d'interfaces web dynamiques, fluides et responsives.</p>
                    <div class="tags-container">
                        <span class="skill-tag">Vue.js</span>
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">HTML/CSS</span>
                        <span class="skill-tag">Tailwind</span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="card-header">
                        <h3>Backend & BDD</h3>
                    </div>
                    <p class="card-desc">Développement d'APIs robustes et gestion de bases de données.</p>
                    <div class="tags-container">
                        <span class="skill-tag">Node.js</span>
                        <span class="skill-tag">Express</span>
                        <span class="skill-tag">PHP</span>
                        <span class="skill-tag">MySQL</span>
                        <span class="skill-tag">MongoDB</span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="card-header">
                        <h3>Outils & Design</h3>
                    </div>
                    <p class="card-desc">Conception UI/UX et gestion collaborative des projets.</p>
                    <div class="tags-container">
                        <span class="skill-tag">Figma</span>
                        <span class="skill-tag">Git/GitHub</span>
                        <span class="skill-tag">VS Code</span>
                        <span class="skill-tag">Agile</span>
                        <span class="skill-tag">UI/UX</span>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script setup>
</script>

<style scoped>
.skills-section {
    padding: 6rem 2rem;
}

.skills-container {
    max-width: 1200px;
    margin: 0 auto;
}

.section-header {
    text-align: center;
    margin-bottom: 4rem;
}

.eyebrow {
    color: var(--accent-blue);
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 0.15em;
    font-size: 0.875rem;
    margin-bottom: 0.5rem;
}

.section-title {
    font-size: 2.5rem;
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

.skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2.5rem; 
}

.skill-card {
    background-color: rgba(255, 255, 255, 0.4); 
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

.icon-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 48px;
    height: 48px;
    background-color: rgba(43, 108, 176, 0.1); 
    border-radius: 12px;
    font-size: 1.5rem;
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
}

.skill-tag:hover {
    background-color: var(--accent-blue);
    color: #ffffff;
    cursor: default;
}

@media (max-width: 768px) {
    .skills-section {
        padding: 4rem 1.5rem;
    }
    
    .section-title {
        font-size: 2rem;
    }
}
</style>