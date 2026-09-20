<script setup lang="ts">
defineProps<{
    title: string
    subtitle?: string
    date: string | number
}>()
</script>

<template>
    <article class="item-card">
        <div class="item-header">
            <div>
                <h3>{{ title }}</h3>
                <p v-if="subtitle" class="subtitle">{{ subtitle }}</p>
            </div>
            <p class="date">{{ date }}</p>
        </div>
        <slot />
    </article>
</template>

<style scoped>

.item-card {
    padding: 1.25rem 0;
    border-bottom: 2px solid #333;
}

.item-card:last-child {
    border-bottom: none;
}

.item-header {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: baseline;
    gap: 1rem;
}

.item-header h3 {
    margin: 0;
    font-size: 1.05rem;
}

.subtitle {
    margin: 0.15rem 0 0;
    color: #aaa;
    font-size: 0.9rem;
}

.date {
    margin: 0;
    color: #888;
    font-size: 0.85rem;
    white-space: nowrap;
}

</style>
