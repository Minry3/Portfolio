<template>
    <section id="veille" class="veille-section">
        <div class="veille-container">
            <SectionHeader title="Veille Technologique" />

            <div class="article-card" :class="{ 'is-open': isOpen }">
                <div class="article-header" @click="toggleVeille">
                    <div class="header-content">
                        <span class="badge-topic">Intelligence Artificielle & Santé</span>
                        <h3>L’essor de l’intelligence artificielle dans la médecine : l’exemple des prothèses bioniques</h3>
                    </div>
                    <button class="toggle-btn">
                        {{ isOpen ? 'Fermer' : 'Cliquer pour en savoir plus' }}
                    </button>
                </div>

                <div class="article-content-wrapper">
                    <div class="article-content-inner">
                        <div class="article-body">
                            <p>
                                L’intelligence artificielle connaît ces derniers temps une expansion démesurable, il s’agit de ce fait d’un sujet incontournable lorsque l’on s’intéresse à l’informatique. Les modèles de réseaux neuronaux deviennent de plus en plus puissants et de nouvelles innovations font leur apparition tous les jours. Un des sujets qui m’a notamment intéressé est celui de l’usage de cette IA dans le domaine médical et plus particulièrement sur les prothèses médicales.
                            </p>

                            <p>
                                Une IA est normalement très énergivore et demande l’usage de nombreux serveurs, surtout pour le stockage de données. Cependant, ces IA peuvent rencontrer des problèmes de latence, et dans le cadre d’une prothèse un long délai pourrait entraîner un déséquilibre voire la chute du patient. Pour pallier cela, il existe ce que l’on nomme le <strong>TinyML</strong>, il s’agit d’une IA embarquée beaucoup plus économe permettant de réaliser des calculs instantanés sans l’utilisation de serveurs. Dans le cadre d’une prothèse bionique, celle-ci peut désormais récupérer les signaux musculaires et en déduire des mouvements pour aider le patient.
                            </p>

                            <p>
                                Je trouve que cette avancée technologique est très importante pour le progrès médical, le fait de pouvoir allier nos compétences pour aider physiquement des individus est d’autant plus intéressant et nous ouvre vers de nouvelles perspectives. D’un côté plus technique, cela permet d’illustrer le défi actuel pour les développeurs pour des logiciels critiques : <strong>coder de façon robuste et mener une phase de tests rigoureuse, car le droit à l’erreur n’existe pas</strong>.
                            </p>
                        </div>

                        <div class="article-footer">
                            <h4>Sources :</h4>
                            <ul class="sources-list">
                                <li>
                                    <a href="https://www.everpuredata.com/fr/knowledge/what-is-healthcare-it.html" target="_blank" rel="noopener noreferrer">
                                        L'informatique de la santé (Everpure Data)
                                    </a>
                                </li>
                                <li>
                                    <a href="https://parcoursmedecin.com/protheses-bioniques-interaction-entre-medecine-et-haute-technologie/" target="_blank" rel="noopener noreferrer">
                                        Prothèses bioniques et haute technologie (Parcours Médecin)
                                    </a>
                                </li>
                                <li>
                                    <a href="https://www.datacamp.com/fr/blog/what-is-tinyml-tiny-machine-learning" target="_blank" rel="noopener noreferrer">
                                        Qu'est-ce que le TinyML ? (DataCamp)
                                    </a>
                                </li>
                            </ul>
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

const isOpen = ref(false);

function toggleVeille() {
    isOpen.value = !isOpen.value;
}
</script>

<style scoped>
.veille-section {
    padding: 8rem 2rem; 
    min-height: 80vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.veille-container {
    max-width: 900px; 
    margin: 0 auto;
}

.article-card {
    background-color: rgba(255, 255, 255, 0.6); 
    border-radius: 20px;
    border: 2px solid var(--accent-blue);
    box-shadow: 8px 8px 0px rgba(43, 108, 176, 0.15); 
    transition: all 0.3s ease;
    overflow: hidden; 
}

.article-card:hover {
    transform: translateY(-4px);
    box-shadow: 12px 12px 0px rgba(43, 108, 176, 0.2);
}

.article-header {
    padding: 2.5rem;
    display: flex;
    flex-direction: column; 
    align-items: flex-start; 
    cursor: pointer; 
    gap: 1.5rem; 
}

.header-content {
    flex: 1;
}

.badge-topic {
    display: inline-block;
    background-color: var(--accent-blue);
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 50px;
    font-size: 0.85rem;
    font-weight: bold;
    margin-bottom: 1rem;
}

.article-header h3 {
    margin: 0;
    font-size: 1.6rem;
    color: var(--text-blue);
    font-weight: 800;
    line-height: 1.3;
}

.toggle-btn {
    background: none;
    border: none;
    color: var(--accent-blue);
    font-weight: 700;
    font-size: 0.85rem; 
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
}

.article-content-wrapper {
    display: grid;
    grid-template-rows: 0fr;
    transition: grid-template-rows 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.article-card.is-open .article-content-wrapper {
    grid-template-rows: 1fr;
}

.article-content-inner {
    overflow: hidden; 
}

.article-body {
    padding: 0 2.5rem;
}

.article-body p {
    color: var(--text-blue);
    opacity: 0.85;
    font-size: 1.05rem;
    line-height: 1.8; 
    margin-bottom: 1.5rem;
    text-align: justify;
}

.article-body strong {
    color: var(--accent-blue);
    font-weight: 700;
}

.article-footer {
    margin: 1.5rem 2.5rem 2.5rem 2.5rem;
    padding-top: 1.5rem;
    border-top: 1px solid rgba(43, 108, 176, 0.2);
}

.article-footer h4 {
    color: var(--text-blue);
    font-size: 1.1rem;
    margin-bottom: 1rem;
}

.sources-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
}

.sources-list a {
    color: var(--text-blue);
    text-decoration: none;
    font-size: 0.95rem;
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    transition: color 0.2s ease;
    opacity: 0.8;
}

.sources-list a:hover {
    color: var(--accent-blue);
    opacity: 1;
    text-decoration: underline;
}

@media (max-width: 768px) {
    .article-header {
        padding: 1.5rem;
    }
    
    .article-header h3 {
        font-size: 1.3rem;
    }

    .article-body, .article-footer {
        padding-left: 1.5rem;
        padding-right: 1.5rem;
    }
    
    .article-footer {
        margin-left: 1.5rem;
        margin-right: 1.5rem;
    }
}
</style>