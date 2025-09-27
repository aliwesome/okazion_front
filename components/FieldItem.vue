<template>
    <div class="bg-orange-500/10 text-orange-500 flex flex-col items-center p-4 rounded-lg w-full md:flex-shrink">
        <HugeiconsIcon :icon="icon" class="mb-2" />
        <h3 class="font-semibold text-sm">{{ title }}</h3>
        <span class="font-light">{{ subtitle }}</span>
    </div>
</template>

<script setup>
import { AiMagicIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

defineProps({
    title: { type: String, default: 'title here' },
    subtitle: { type: String, default: 'title here' },
    icon: { type: [String, Object], default: () => AiMagicIcon },
})
</script>