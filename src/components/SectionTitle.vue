<script setup lang="ts">
import TypeText from './TypeText.vue'

defineProps<{
    text: string
}>()
</script>

<template>
    <h2><TypeText :text="text" /></h2>
</template>

<style scoped>

h2 {
    color: var(--accent);
}

</style>
