<template>
    <footer class="footer-section">
        <div class="footer-container">
            <p>&copy; {{ currentYear }} Noémie CHHUN. Tous droits réservés.</p>
        </div>
    </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear();
</script>

<style scoped>
.footer-section {
    background-color: var(--text-blue);
    padding: 2rem;
    color: var(--bg-beige);
}

.footer-container {
    max-width: 1200px;
    margin: 0 auto;
    text-align: center; 
}

.footer-container p {
    margin: 0;
    font-size: 0.95rem;
    opacity: 0.8;
}
</style>