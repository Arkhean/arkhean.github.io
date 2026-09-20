<script setup lang="ts">
import SectionTitle from './SectionTitle.vue'
</script>

<template>
    <SectionTitle text="Contact" />
    <div class="contact-content">
        <p class="contact-text">
            N'hésitez pas à me contacter via LinkedIn.
        </p>
        <a
            class="linkedin-button"
            href="https://www.linkedin.com/in/julien-miens-328243170"
            target="_blank"
            rel="noopener noreferrer"
        >
            Me contacter sur LinkedIn
        </a>
    </div>
</template>

<style scoped>

.contact-content {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 1.5rem;
    margin-top: 1.5rem;
}

.contact-text {
    line-height: 1.6;
    color: #ddd;
}

.linkedin-button {
    display: inline-block;
    padding: 0.6rem 1.4rem;
    border: 1px solid var(--accent);
    border-radius: 6px;
    color: var(--accent);
    text-decoration: none;
    font-size: 0.95rem;
    transition: background-color 0.15s, color 0.15s;
}

.linkedin-button:hover {
    background-color: var(--accent);
    color: black;
}

</style>
