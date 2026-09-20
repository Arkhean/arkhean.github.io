<script setup lang="ts">
import ItemCard from './ItemCard.vue'

defineProps<{
    degree: string
    school: string
    period: string
    description: string
}>()
</script>

<template>
    <ItemCard :title="degree" :subtitle="school" :date="period">
        <p class="description">{{ description }}</p>
    </ItemCard>
</template>

<style scoped>

.description {
    margin: 0.6rem 0 0;
    line-height: 1.6;
    color: #ddd;
}

</style>
