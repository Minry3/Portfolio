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
                            <p v-html="project.details"></p>
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
import imgMediaTek from '../assets/Projets/mediaTek.png';
import imgOwlearning from '../assets/Projets/owlearning.png';
import imgSort from '../assets/Projets/on-sort.png';

const openProject = ref(null);

function toggleProject(title) {
    openProject.value = openProject.value === title ? null : title;
}

const projects = [
    { 
        title: "Jeu d'échecs", 
        year: "2025",
        details: `Création d’un jeu d’échecs en Java, dans le cadre de mon BUT Informatique. Celui-ci peut être lancé à partir d’un terminal comme celui de Linux. Il s’agit d’une partie simplifiée, permettant de détecter les cas de pat ainsi que d’échec et mat.

                La programmation du jeu a été réalisée de façon collaborative en duo à l’aide de Git.

                <strong>Objectif :</strong> 
                Comprendre et maîtriser la programmation orientée objet dans un contexte concret.

                <strong>Étapes de réalisation :</strong>
                Nous avons réalisé une modélisation UML initiale qui a permis de comprendre la logique de notre programme, mais aussi qui nous a aidés à optimiser notre répartition de travail. 

                Je me suis ensuite chargée de la conception des classes qui m'étaient assignées. J’ai donc développé les méthodes nécessaires, notamment celles liées au déplacement des pièces qui pouvaient parfois demander la création d’un algorithme plus complexe que d’autres.
                
                En parallèle de cela, je me suis chargée du développement des exceptions pour sécuriser la saisie des joueurs et du déploiement de la documentation technique à l’aide de Javadoc.`,
        tags: ["Java", "Git"],
        image: imgEchec, 
        github: "https://github.com/Minry3/Jeu-echec-java" 
    },
    { 
        title: "MediaTek86", 
        year: "2024",
        details: `Création d’une application de bureau pour gérer le personnel d’un réseau de médiathèques, dans le cadre du BTS SIO.

                <strong>Objectif :</strong> 
                Conception d’une application de bureau avec une architecture structurée autour du modèle de conception MVC.

                Les responsables peuvent se connecter de manière sécurisée via des mots de passe hachés afin de gérer le personnel de chaque médiathèque. Ils peuvent également ajouter, modifier ou supprimer des profils, et gérer leurs affectations aux différents services ainsi que leurs absences.

                <strong>Étapes de réalisation : </strong>
                J’ai tout d’abord effectué les maquettes des différentes interfaces et créé la base de données relationnelle avec MySQL.

                L’application a été codée en C# via Visual Studio en veillant à respecter scrupuleusement l’architecture MVC.

                Enfin, un installeur exécutable a été généré pour permettre le déploiement local de l’application de façon autonome.

                Ce projet a été réalisé entièrement de manière individuelle, toute l’organisation s’est faite via un tableau Kanban et le dépôt GitHub. `,
        tags: ["C#", "SQL", "Visual Studio"],
        image: imgMediaTek, 
        github: "https://github.com/Minry3/MediaTek86" 
    },
    { 
        title: "OWLearning", 
        year: "2025-2026",
        details: `Création d’une application web d’apprentissage en ligne de façon collaborative, dans le cadre d’un projet tutoré de BUT Informatique.

                <strong>Objectif : </strong>
                Conception, développement et déploiement d’une application de e-learning. L’enjeu majeur était de créer une architecture respectant les principes de conception SOLID.

                Les utilisateurs ont la possibilité de s’inscrire, suivre des cours, leur progression et envoyer des messages aux créateurs. De même, chaque créateur a la possibilité de créer et publier du contenu pédagogique.

                <strong>Étapes de réalisation :</strong>
                Nous avons modélisé et créé une API REST en Java avec Spring Boot, en veillant à ce que les principes SOLID soient respectés. Un travail important de refactorisation a notamment été réalisé afin de consolider l’architecture.

                Un client léger a ensuite été développé en vue.js avec l’utilisation de bootstrap-vue-next, permettant la consommation des endpoints via une interface web responsive.

                Enfin, l'entièreté du projet est conteneurisée avec Docker.

                Chaque phase du projet a été réalisée sous forme de sprint avec la désignation d’un manager. De ce fait, cela a permis à l’intégralité des membres d’intervenir sur l’ensemble des étapes de réalisation.`,
        tags: ["SpringBoot", "Vue.js", "SQL", "Docker"],
        image: imgOwlearning, 
        github: "https://github.com/OWLearning-Project/OWLearning" 
    },
    { 
        title: "On Sort ? (Projet en cours)", 
        year: "2026",
        details: `Application web permettant de savoir si la température extérieure est convenable pour sortir son chien.

                En raison des fortes canicules qu’il y a pu y avoir récemment, une des problématiques qui revenait souvent en tant que propriétaire canin était de savoir si la température dehors n’était pas trop élevée pour pouvoir laisser mon animal sortir sans se brûler les pattes. Notre sensibilité étant différente de celle des animaux, je me suis demandé s’il n’était pas possible de créer un outil permettant d’obtenir cette information en un clic.

                En recherchant sur internet, j’ai vu qu’il existait des API open source permettant de récupérer les données météorologiques en direct telles que la température au sol.

                Afin de m’entraîner, j’ai donc créé un site en vue.js permettant de consommer les données de cette API et de les traiter pour afficher un diagnostic instantané et une recommandation adaptée avant chaque promenade. 

                Ce site est encore en phase de développement, l'algorithme de calcul étant en cours d'affinage pour garantir des résultats parfaitement précis.`,
        tags: ["Vue.js", "API"],
        image: imgSort, 
        github: "https://github.com/Minry3/OnSort" 
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