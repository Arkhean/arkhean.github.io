<script setup lang="ts">
import ItemCard from './ItemCard.vue'
import StackTags from './StackTags.vue'

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
    <ItemCard :title="title" :subtitle="company" :date="period">
        <StackTags :stack="stack" />
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
    </ItemCard>
</template>

<style scoped>

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

</style>
