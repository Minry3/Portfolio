<template>
  <section class="hero-section">
    <div class="hero-content">
      
      <div class="hero-title-container">
        <h1 class="name">Noémie CHHUN</h1>
        <p class="job-title">Développeuse FullStack</p>
      </div>
      
      <p class="description">
        Étudiante en deuxième année de BUT Informatique au sein de l'IUT de Villetaneuse, en alternance chez Salvia Développement.
      </p>

      <div class="contact-email">
        <a href="mailto:noemiechhun@gmail.com" class="email-link">
          <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="envelope-icon">
            <rect width="20" height="16" x="2" y="4" rx="2"></rect>
            <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"></path>
          </svg>
          noemiechhun@gmail.com
        </a>
      </div>

      <div class="actions">
        <a href="CV_Noemie_CHHUN.pdf" target="_blank" rel="noopener noreferrer" class="btn-cv">
          Voir mon CV
        </a>
        
        <div class="social-links">
          <a href="https://github.com/Minry3" target="_blank" class="social-btn">GitHub</a>
          <a href="https://www.linkedin.com/in/noemie-chhun/" target="_blank" class="social-btn">LinkedIn</a>
        </div>
      </div>
    </div>

    <div class="hero-image-container">
      <div class="image-wrapper">
        <img src="../assets/profil.png" alt="Ma photo de profil" class="profile-pic">
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.hero-section {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 80px 40px; 
  max-width: 1200px;
  margin: 0 auto; 
  gap: 40px;
}

.hero-content {
  flex: 1;
  max-width: 600px;
}

.hero-title-container {
  margin-bottom: 32px; 
}

.name {
  font-size: 4.5rem;
  font-weight: 700;
  color: var(--text-blue, #1A365D);
  line-height: 1.1;
  margin-bottom: 8px;
  font-family: 'Playfair Display', 'Georgia', serif; 
  letter-spacing: -1px; 
}

.job-title {
  font-size: 1.5rem; 
  font-weight: 600;
  color: var(--accent-blue, #1E40AF); 
  text-transform: uppercase; 
  letter-spacing: 3px; 
}

.description {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 25px;
  color: var(--text-blue, #1A365D);
  opacity: 0.9;
}

.contact-email {
  margin-bottom: 35px;
}

.email-link {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  color: var(--accent-blue, #1E40AF);
  text-decoration: none;
  font-size: 1.1rem;
  font-weight: 600;
  transition: all 0.3s ease;
}

.email-link:hover {
  color: var(--text-blue, #1A365D);
  transform: translateX(5px);
}

.envelope-icon {
  stroke: var(--accent-blue, #1E40AF);
  transition: stroke 0.3s ease;
}

.email-link:hover .envelope-icon {
  stroke: var(--text-blue, #1A365D);
}

.actions {
  display: flex;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
}

.btn-cv {
  display: flex;
  align-items: center;
  gap: 8px;
  background-color: var(--accent-blue, #1E40AF);
  color: white;
  padding: 12px 24px;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-cv:hover {
  background-color: var(--text-blue, #1A365D);
  transform: translateY(-2px);
}

.social-links {
  display: flex;
  gap: 12px;
}

.social-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 12px 20px;
  background-color: var(--accent-blue, #1E40AF);
  color: white;
  border-radius: 50px;
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: bold;
  transition: all 0.3s ease;
}

.social-btn:hover {
  background-color: var(--text-blue, #1A365D);
  transform: translateY(-2px);
}

.hero-image-container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-wrapper {
  position: relative;
  width: 100%;
  max-width: 550px; 
  height: 650px;    
  display: flex;
  justify-content: center;
  align-items: flex-end; 
}

.profile-pic {
  position: relative;
  z-index: 1; 
  height: 100%; 
  width: auto;
  max-width: 140%; 
  object-fit: contain; 
  filter: drop-shadow(0px 15px 25px rgba(0, 0, 0, 0.15));
  transform: scale(1.15); 
  transform-origin: bottom center; 
}

@media (max-width: 900px) {
  .hero-section {
    flex-direction: column-reverse;
    text-align: center;
    padding: 20px 20px 40px 20px; 
    gap: 0; 
  }
  
  .hero-title-container {
    margin-bottom: 20px;
  }
  
  .contact-email {
    display: flex;
    justify-content: center;
    margin-bottom: 25px;
  }

  .actions {
    justify-content: center;
    flex-wrap: wrap;
  }
  
  .name {
    font-size: 2.8rem;
  }
  .job-title {
    font-size: 1.1rem;
    letter-spacing: 2px;
  }

  .image-wrapper {
    height: 320px; 
    max-width: 320px;
    margin-bottom: 10px; 
  }
}
</style>