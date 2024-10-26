<script setup lang="ts">
import { computed } from 'vue';
import GithubIcon from './icons/Github.vue';
import LinkedInIcon from './icons/LinkedIn.vue';
import TikTokIcon from './icons/TikTok.vue';
import WebsiteIcon from './icons/Website.vue';

interface Social {
    name: string
    url: string
    icon?: string
}

const props = defineProps<{ social: Social }>()
const logo = computed(() => {
    switch (props.social.icon) {
        case 'github':
            return GithubIcon;
        case 'linkedin':
            return LinkedInIcon;
        case 'tiktok':
            return TikTokIcon;
        default:
            return WebsiteIcon;
    }
})
</script>
<template>
    <a :href="social.url" target="_blank"
        class="w-full flex items-center justify-between rounded-lg border-2 dark:border dark:border-zinc-300 border-zinc-600 p-4 hover:text-emerald-600 hover:border-emerald-600 dark:hover:text-emerald-300 dark:hover:border-emerald-300 hover:scale-105 transition-transform duration-300 ease-in-out">
        <component :is="logo" class="w-6 h-6" /> {{ social.name }}
        <button />
    </a>
</template>