<template>
    <section id="about" class="about-section">
        <div class="about-container">
            <div class="section-header">
                <p class="eyebrow">Apprenez à me connaître</p>
                <h2 class="section-title">À propos de moi</h2>
            </div>
            
            <div class="about-content">
                <div class="intro-text">
                    <p>Je m'appelle <span class="highlight">Noémie Chhun</span>. J’ai toujours aimé comprendre comment les choses sont créées. Pour moi, l’informatique est comparable à des Lego : comment l’assemblage de certains éléments permet-il d’atteindre ce résultat final ? Cette curiosité, née au lycée, continue de me guider chaque jour.</p>
                    
                    <p>Actuellement, je suis en deuxième année de BUT Informatique au sein de l'IUT de Villetaneuse, tout en évoluant comme apprentie R&D chez Salvia Développement. Je suis spécialisée dans la conception de logiciels et d'applications. J'aime notamment créer des outils répondant à des besoins spécifiques.</p>
                    
                    <p class="objectif-texte">Mon objectif ? Concevoir des solutions intuitives pour améliorer et simplifier le quotidien des utilisateurs.</p>   
                    
                    <p>En rassemblant toutes ces connaissances, j'aimerais à terme pouvoir intégrer une école d’ingénieur et finaliser ma formation pour devenir ingénieure dans la conception logicielle et réaliser mon objectif initial.</p>
                    
                    <p>Pour en connaître davantage sur mes compétences, mon parcours et mes projets, n’hésitez pas à poursuivre l’exploration de ce portfolio.</p>
                    
                    <h4><strong>En vous souhaitant une bonne visite !</strong></h4>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
</script>

<style scoped>
.about-section {
    background-color: var(--accent-blue); 
    padding: 6rem 2rem; 
    display: flex;
    justify-content: center; 
    align-items: center;
    box-shadow: inset 0 4px 10px rgba(0, 0, 0, 0.05);
    width: 100vw;
    margin-left: calc(-50vw + 50%);
}

.about-container {
    max-width: 900px;
    margin: 0 auto;
}

.section-header {
    text-align: center; 
    margin-bottom: 2.5rem;
}

.eyebrow {
    color: rgba(248, 244, 230, 0.7); 
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 0.15em;
    font-size: 0.875rem;
    margin-bottom: 1rem;
}

.section-title {
    font-size: 3rem;
    color: var(--bg-beige, #f8f4e6); 
    margin: 0;
    font-weight: 800;
}

.about-content {
    background-color: var(--bg-beige, #f8f4e6); 
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

.objectif-texte {
    font-weight: 600; 
    text-align: left; 
    margin: 2.5rem 0;
    padding: 1.5rem 2rem;
    background-color: rgba(0, 0, 0, 0.03); 
    border: 1px solid rgba(0, 0, 0, 0.1);
    border-left: 4px solid var(--accent-blue, #0056b3); 
    border-radius: 8px;
    color: #1a252f; 
}

.intro-text h4 {
    text-align: center;
    margin-top: 3rem;
    color: var(--accent-blue, #0056b3);
    font-size: 1.2rem;
}

@media (max-width: 768px) {
    .about-section {
        padding: 4rem 1.5rem; 
    }

    .section-title {
        font-size: 2.25rem;
    }
    
    .about-content {
        padding: 2rem 1.5rem; 
    }
    
    .intro-text {
        font-size: 1.05rem;
        text-align: left; 
    }
    
    .objectif-texte {
        padding: 1.2rem;
        margin: 2rem 0;
    }
}
</style>