<template>
    <section id="about" class="about-section section-full-dark">
        <div class="bg-decorations-wrapper">
            <div class="blob blob-about-1"></div>
            <div class="blob blob-about-2"></div>
            <div class="dots dots-about-1"></div>
        </div>

        <div class="about-container">
            <SectionHeader title="À propos de moi" />
            
            <div class="about-content">
                <div class="intro-text">
                    <p>Bonjour, moi c'est <span class="highlight">Noémie Chhun</span> ! J’ai toujours aimé comprendre comment les choses sont créées. Pour moi, l’informatique est comparable à un voyage constant: nous découvrons toujours de nouvelles technologies, et essayons de comprendre comment elles peuvent nous être utiles. Cette curiosité, née au lycée, continue de me guider chaque jour.</p>
                    <p>Actuellement, je suis en deuxième année de BUT Informatique au sein de l'IUT de Villetaneuse, tout en évoluant comme apprentie R&D chez Salvia Développement. Je suis spécialisée dans la conception de logiciels et d'applications. J'aime notamment créer des outils répondant à des besoins spécifiques.</p>
                    <div class="objectif-card">
                        <h3>Mon objectif ?</h3>
                        <p>Concevoir des solutions intuitives pour améliorer et simplifier le quotidien des utilisateurs.</p>
                    </div>                    
                    <p>En rassemblant toutes ces connaissances, j'aimerais à terme pouvoir intégrer une école d’ingénieur et finaliser ma formation pour devenir ingénieure dans la conception logicielle et réaliser mon objectif initial.</p>
                    <p>Pour en connaître davantage sur mes compétences, mon parcours et mes projets, n’hésitez pas à poursuivre l’exploration de ce portfolio.</p>
                    <h4 class="conclusion-text"><strong>En vous souhaitant une bonne visite !</strong></h4>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import SectionHeader from './SectionHeader.vue';
</script>

<style scoped>
.about-section {
    padding: 6rem 2rem; 
    display: flex;
    justify-content: center; 
    align-items: center;
    box-shadow: inset 0 4px 10px rgba(0, 0, 0, 0.05);
}

@keyframes morph {
    0%, 100% { border-radius: 40% 60% 70% 30% / 40% 40% 60% 50%; }
    34% { border-radius: 70% 30% 50% 50% / 30% 30% 70% 70%; }
    67% { border-radius: 100% 60% 60% 100% / 100% 100% 60% 60%; }
}

.blob {
    position: absolute;
    background: rgba(248, 244, 230, 0.04); 
    animation: morph 12s ease-in-out infinite;
}

.blob-about-1 {
    top: -15%; right: -10%;
    width: 550px; height: 550px;
    background: rgba(248, 244, 230, 0.03);
}

.blob-about-2 {
    bottom: -15%; left: -5%;
    width: 350px; height: 350px;
    background: rgba(248, 244, 230, 0.05);
    animation-delay: -4s; 
}

.dots {
    position: absolute;
    background-image: radial-gradient(rgba(248, 244, 230, 0.15) 2px, transparent 2px);
    background-size: 20px 20px;
}

.dots-about-1 {
    top: 10%; left: 5%;
    width: 250px; height: 250px;
    border-radius: 50%;
    opacity: 0.6;
}

.about-container {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
}

.about-content {
    background-color: var(--bg-beige);
    padding: 3rem 4rem;
    border-radius: 16px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15); 
}

.intro-text {
    font-size: 1.1rem; 
    line-height: 1.8;
    color: #2c3e50; 
    margin: 0;
    text-align: justify;
}

.intro-text p {
    margin-bottom: 1.5rem;
}

.intro-text p:last-child {
    margin-bottom: 0;
}

.highlight {
    font-weight: 800;
    color: var(--accent-blue, #0056b3); 
}

.objectif-card {
    background-color: rgba(255, 255, 255, 0.6); 
    border-radius: 16px;
    padding: 1.5rem 2rem;
    margin: 2.5rem 0;
    border: 2px solid var(--accent-blue);
    box-shadow: 6px 6px 0px rgba(43, 108, 176, 0.15); 
    transition: all 0.3s ease;
    text-align: center;
}

.objectif-card h3 {
    margin: 0 0 0.5rem 0;
    font-size: 1.35rem;
    color: var(--accent-blue, #2b6cb0);
    font-weight: 800;
}

.intro-text .objectif-card p {
    color: var(--text-blue, #2c3e50);
    font-size: 1.15rem;
    font-weight: 600;
    margin: 0; 
    text-align: center;
}

.conclusion-text {
    text-align: center;
    margin-top: 3rem;
    color: var(--accent-blue, #0056b3);
    font-size: 1.2rem;
}

@media (max-width: 768px) {
    .about-content {
        padding: 2rem 1.5rem; 
    }
    
    .intro-text {
        font-size: 1.05rem;
        text-align: justify; 
    }
    
    .objectif-card {
        padding: 1.5rem;
        margin: 2rem 0;
    }
}
</style>