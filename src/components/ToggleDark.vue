<script setup lang="ts">
import { useDark, useToggle } from '@vueuse/core'
import MoonIcon from './icons/Moon.vue'
import SunIcon from './icons/Sun.vue'

const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>
<template>
    <button aria-label="Toggle dark mode"
        class="m-2 p-1.5 rounded-lg border-2 dark:border dark:border-zinc-300 border-zinc-600 hover:text-emerald-600 hover:border-emerald-600 dark:hover:text-emerald-300 dark:hover:border-emerald-300 hover:scale-105 transition-transform duration-300 ease-in-out"
        @click="toggleDark()">
        <SunIcon v-if="isDark" class="size-5" />
        <MoonIcon v-else class="size-5" />
    </button>
</template>