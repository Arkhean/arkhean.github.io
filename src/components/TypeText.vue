<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'

const props = defineProps<{
    text: string
}>()

const CHAR_INTERVAL_MS = 100
const CURSOR_BLINK_MS = 500
const CURSOR_HIDE_DELAY_MS = 600

const displayedLength = ref(0)
const cursorVisible = ref(true)
const showCursor = ref(true)
let typeIntervalId: ReturnType<typeof setInterval> | undefined
let blinkIntervalId: ReturnType<typeof setInterval> | undefined
let hideTimeoutId: ReturnType<typeof setTimeout> | undefined

function type() {
    typeIntervalId = setInterval(() => {
        if (displayedLength.value < props.text.length) {
            displayedLength.value++
        } else {
            clearInterval(typeIntervalId)
            hideTimeoutId = setTimeout(() => {
                clearInterval(blinkIntervalId)
                showCursor.value = false
            }, CURSOR_HIDE_DELAY_MS)
        }
    }, CHAR_INTERVAL_MS)
}

onMounted(() => {
    type()
    blinkIntervalId = setInterval(() => {
        cursorVisible.value = !cursorVisible.value
    }, CURSOR_BLINK_MS)
})

onBeforeUnmount(() => {
    clearInterval(typeIntervalId)
    clearInterval(blinkIntervalId)
    clearTimeout(hideTimeoutId)
})
</script>

<template>
    <span>{{ text.slice(0, displayedLength) }}<span v-if="showCursor" class="cursor" :class="{ hidden: !cursorVisible }">|</span></span>
</template>

<style scoped>

.cursor {
    display: inline-block;
    color: var(--accent);
}

.cursor.hidden {
    opacity: 0;
}

</style>
