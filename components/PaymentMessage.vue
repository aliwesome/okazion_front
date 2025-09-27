<template>
    <div class="flex flex-col items-center gap-y-4 text-green-500 mb-6">
        <HugeiconsIcon :icon="icon" :class="iconClass + ' w-14 h-14 p-3 rounded-lg'" />
        <h3 class="text-center md:text-lg font-black">{{ title }}</h3>
    </div>
</template>

<script setup>
import { CheckmarkBadge02Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

defineProps({
    title: { type: String, default: 'عنوان' },
    icon: { type: [String, Object], default: () => CheckmarkBadge02Icon },
    iconClass: {
        type: String,
        default: 'bg-green-500/10 text-green-500'
    }
})
</script>