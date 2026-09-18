<script setup lang="ts">
defineProps<{
    title: string
    year: number
    description: string
    stack: string[]
    url: string
}>()
</script>

<template>
    <article class="project-item">
        <div class="project-header">
            <h3>{{ title }}</h3>
            <p class="year">{{ year }}</p>
        </div>
        <ul class="stack">
            <li v-for="tech in stack" :key="tech">{{ tech }}</li>
        </ul>
        <p class="description">{{ description }}</p>
        <a class="github-link" :href="url" target="_blank" rel="noopener noreferrer">
            {{ url }}
        </a>
    </article>
</template>

<style scoped>

.project-item {
    padding: 1.25rem 0;
    border-bottom: 2px solid #333;
}

.project-item:last-child {
    border-bottom: none;
}

.project-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 1rem;
}

.project-header h3 {
    margin: 0;
    font-size: 1.05rem;
}

.year {
    margin: 0;
    color: #888;
    font-size: 0.85rem;
    white-space: nowrap;
}

.stack {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin: 1rem 0 0;
    padding: 0;
    list-style: none;
}

.stack li {
    padding: 0.2rem 0.6rem;
    border: 1px solid var(--accent);
    border-radius: 999px;
    color: var(--accent);
    font-size: 0.9rem;
}

.description {
    margin: 0.6rem 0 0;
    line-height: 1.6;
    color: #ddd;
}

.github-link {
    display: inline-block;
    margin-top: 0.75rem;
    color: var(--accent);
    text-decoration: none;
    font-size: 0.9rem;
    overflow-wrap: anywhere;
    border-bottom: 1px solid transparent;
    transition: border-color 0.15s;
}

.github-link:hover {
    border-bottom-color: var(--accent);
}

</style>
