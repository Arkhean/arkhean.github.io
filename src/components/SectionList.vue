<script setup lang="ts">
import SectionTitle from './SectionTitle.vue'

defineProps<{
    title: string
}>()
</script>

<template>
    <SectionTitle :text="title" />
    <slot name="intro" />
    <div class="section-list">
        <slot />
    </div>
</template>

<style scoped>

.section-list {
    margin-top: 1.5rem;
    margin-right: 20%;
}

@media (max-width: 768px) {
    .section-list {
        margin-right: 0;
    }
}

</style>
