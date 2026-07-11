<template>
    <section id="education" class="education-section">
        <div class="bg-decorations">
            <div class="blob blob-1"></div>
            <div class="dots dots-1"></div>
        </div>

        <div class="education-container">
            <div class="section-header">
                <p class="eyebrow">Mon Parcours</p>
                <h2 class="section-title">Formation</h2>
            </div>

            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <span class="date-badge">2024 - Présent</span>
                        <h3>BUT Informatique</h3>
                        <h4 class="school">Université Sorbonne Paris Nord - IUT de Villetaneuse</h4>
                        <p>Développement d'applications mobiles et web, algorithmique, bases de données, systèmes et réseaux, management</p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <span class="date-badge">2023 - 2024</span>
                        <h3>Première année de BTS Services Informatiques aux Organisations</h3>
                        <h4 class="school">CNED</h4>
                        <p>Option: Solutions Logicielles et Applications Métiers <br/> Avis de passage en deuxième année obtenu</p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <span class="date-badge">2020 - 2023</span>
                        <h3>Baccalauréat Général</h3>
                        <h4 class="school">Lycée René Cassin - Gonesse</h4>
                        <p>Spécialités: Mathématiques, Numérique et Sciences Informatiques (NSI) <br/> Mention très bien avec les félicitations du jury</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
    const items = document.querySelectorAll('.timeline-item');
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('is-visible');
                observer.unobserve(entry.target); 
            }
        });
    }, { threshold: 0.05 }); 

    items.forEach(item => {
        observer.observe(item);
    });
});
</script>

<style scoped>
.education-section {
    position: relative;
    padding: 6rem 2rem;
    overflow: hidden;
    background-color: var(--accent-blue);
    width: 100vw;
    margin-left: calc(-50vw + 50%);
}

.bg-decorations {
    position: absolute;
    top: 0; left: 0; width: 100%; height: 100%;
    overflow: hidden;
    pointer-events: none; 
    z-index: 0;
}

@keyframes morph {
    0%, 100% { border-radius: 40% 60% 70% 30% / 40% 40% 60% 50%; }
    34% { border-radius: 70% 30% 50% 50% / 30% 30% 70% 70%; }
    67% { border-radius: 100% 60% 60% 100% / 100% 100% 60% 60%; }
}

.blob {
    position: absolute;
    background: rgba(248, 244, 230, 0.03); 
    animation: morph 12s ease-in-out infinite;
}

.blob-1 {
    top: -10%; left: -5%;
    width: 400px; height: 400px;
    background: rgba(248, 244, 230, 0.04);
}

.dots {
    position: absolute;
    background-image: radial-gradient(rgba(248, 244, 230, 0.15) 2px, transparent 2px);
    background-size: 20px 20px;
}

.dots-1 {
    bottom: 5%; right: 5%;
    width: 250px; height: 250px;
    border-radius: 50%;
    opacity: 0.7;
}

.education-container {
    position: relative;
    z-index: 1; 
    max-width: 900px; 
    margin: 0 auto;
}

.section-header { text-align: center; margin-bottom: 5rem; }

.eyebrow {
    color: rgba(248, 244, 230, 0.7); 
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 0.15em;
    font-size: 0.875rem;
    margin-bottom: 0.5rem;
}

.section-title {
    font-size: 2.5rem;
    color: var(--bg-beige); 
    margin: 0;
    font-weight: 800;
    position: relative;
    display: inline-block;
    padding-bottom: 1rem;
}

.section-title::after {
    content: "";
    position: absolute;
    bottom: 0; left: 50%; transform: translateX(-50%);
    width: 70px; height: 5px;
    background: var(--bg-beige); 
    border-radius: 3px;
}

.timeline { position: relative; }

.timeline::after {
    content: ''; 
    position: absolute;
    width: 4px; 
    background-color: rgba(248, 244, 230, 0.2); 
    top: 0; 
    bottom: 0; 
    left: 20px; 
    border-radius: 4px;
    z-index: 0; 
}

.timeline-item {
    position: relative; width: 100%;
    padding-left: 60px; margin-bottom: 3rem; 
    opacity: 0; transform: translateY(50px);
    transition: opacity 0.6s ease-out, transform 0.6s ease-out;
}

.timeline-item:last-child { margin-bottom: 0; }
.timeline-item.is-visible { opacity: 1; transform: translateY(0); }

.timeline-dot {
    position: absolute; 
    width: 24px; 
    height: 24px;
    background-color: var(--accent-blue); 
    border: 4px solid var(--bg-beige);
    border-radius: 50%; 
    top: 30px; 
    left: 10px; 
    z-index: 2; 
    box-shadow: 0 0 0 4px rgba(248, 244, 230, 0.1); 
}
.timeline-content {
    background-color: rgba(248, 244, 230, 0.05); 
    backdrop-filter: blur(4px); padding: 2rem;
    border-radius: 16px; border: 1px solid rgba(248, 244, 230, 0.3); 
    box-shadow: 6px 6px 0px rgba(0, 0, 0, 0.1); 
    position: relative;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.timeline-content:hover {
    transform: translate(-4px, -4px);
    box-shadow: 10px 10px 0px rgba(0, 0, 0, 0.2);
    border-color: rgba(248, 244, 230, 0.6);
}

.date-badge {
    display: inline-block; background-color: var(--bg-beige); 
    color: var(--accent-blue); padding: 0.4rem 1rem;
    border-radius: 50px; font-size: 0.85rem; font-weight: 700; margin-bottom: 1rem;
}

.timeline-content h3 { margin: 0 0 0.5rem 0; color: var(--bg-beige); font-size: 1.25rem; font-weight: 800; }
.school { margin: 0 0 1rem 0; color: rgba(248, 244, 230, 0.8); font-size: 1rem; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; }
.timeline-content p { margin: 0; color: var(--bg-beige); opacity: 0.9; line-height: 1.6; font-size: 0.95rem; }

@media screen and (max-width: 768px) {
    .education-section { padding: 4rem 1.5rem; }
    .timeline-item { padding-left: 45px; }
    .timeline::after { left: 10px; }
    .timeline-dot { left: 0px; width: 20px; height: 20px; top: 25px; }
    .timeline-content { padding: 1.5rem; }
}
</style>