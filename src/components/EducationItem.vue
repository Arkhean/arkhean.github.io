<script setup lang="ts">
defineProps<{
    degree: string
    school: string
    period: string
    description: string
}>()
</script>

<template>
    <article class="education-item">
        <div class="education-header">
            <div>
                <h3>{{ degree }}</h3>
                <p class="school">{{ school }}</p>
            </div>
            <p class="period">{{ period }}</p>
        </div>
        <p class="description">{{ description }}</p>
    </article>
</template>

<style scoped>

.education-item {
    padding: 1.25rem 0;
    border-bottom: 2px solid #333;
}

.education-item:last-child {
    border-bottom: none;
}

.education-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 1rem;
}

.education-header h3 {
    margin: 0;
    font-size: 1.05rem;
}

.school {
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

.description {
    margin: 0.6rem 0 0;
    line-height: 1.6;
    color: #ddd;
}

</style>
