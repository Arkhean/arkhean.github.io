<script setup lang="ts">
import ItemCard from './ItemCard.vue'
import StackTags from './StackTags.vue'

defineProps<{
    title: string
    year: number
    description: string
    stack: string[]
    url: string
}>()
</script>

<template>
    <ItemCard :title="title" :date="year">
        <StackTags :stack="stack" />
        <p class="description">{{ description }}</p>
        <a class="github-link" :href="url" target="_blank" rel="noopener noreferrer">
            {{ url }}
        </a>
    </ItemCard>
</template>

<style scoped>

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
