<template>
    <div class="section-header">
        <h2 class="section-title">{{ title }}</h2>
    </div>
</template>

<script setup>
defineProps({
    title: {
        type: String,
        required: true
    }
});
</script>