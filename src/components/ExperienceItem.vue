<script setup lang="ts">
defineProps<{
    title: string
    company: string
    period: string
    context: string
    achievements: string[]
    stack: string[]
}>()

function parseBold(text: string) {
    return text.split('**').map((part, i) => ({ text: part, bold: i % 2 === 1 }))
}
</script>

<template>
    <article class="experience-item">
        <div class="experience-header">
            <div>
                <h3>{{ title }}</h3>
                <p class="company">{{ company }}</p>
            </div>
            <p class="period">{{ period }}</p>
        </div>
        <ul class="stack">
            <li v-for="tech in stack" :key="tech">{{ tech }}</li>
        </ul>
        <h4>Contexte</h4>
        <p class="context">{{ context }}</p>
        <h4>Réalisations</h4>
        <ul class="achievements">
            <li v-for="achievement in achievements" :key="achievement">
                <template v-for="(part, i) in parseBold(achievement)" :key="i">
                    <strong v-if="part.bold">{{ part.text }}</strong>
                    <template v-else>{{ part.text }}</template>
                </template>
            </li>
        </ul>

    </article>
</template>

<style scoped>

.experience-item {
    padding: 1.25rem 0;
    border-bottom: 2px solid #333;
}

.experience-item:last-child {
    border-bottom: none;
}

.experience-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 1rem;
}

.experience-header h3 {
    margin: 0;
    font-size: 1.05rem;
}

.company {
    margin: 0.15rem 0 0;
    color: #aaa;
    font-size: 0.9rem;
}

.period {
    margin: 0;
    color: #888;
    font-size: 0.85rem;
    white-space: nowrap;
}

.context {
    margin: 0.6rem 0 0;
    line-height: 1.6;
    color: #ddd;
}

.achievements {
    margin: 0.75rem 0 0;
    padding-left: 1.1rem;
    line-height: 1.6;
    color: #ddd;
}

.achievements li {
    margin-bottom: 0.35rem;
}

.achievements strong {
    color: white;
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

</style>
