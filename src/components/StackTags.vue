<script setup lang="ts">
defineProps<{
    stack: string[]
}>()
</script>

<template>
    <ul class="stack">
        <li v-for="tech in stack" :key="tech">{{ tech }}</li>
    </ul>
</template>

<style scoped>

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
