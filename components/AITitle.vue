<template>
    <div class="flex items-center justify-between gap-4 border-b border-gray-200  py-4">
        <div class="flex items-center gap-4">
            <!-- icon -->
            <div class="p-2 rounded-lg bg-orange-500/15 text-orange-500">
                <HugeiconsIcon :icon="icon" />
            </div>
            <h5 class="text-sm font-semibold text-black">{{ title }}</h5>
        </div>
        <h6 class=" hidden md:block capitalize text-base text-gray-400 font-extralight">{{ en }}</h6>
    </div>
</template>

<script setup>
import { GridIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

defineProps({
    title: { type: String, default: 'عنوان' },
    en: { type: String, default: 'en title' },
    icon: { type: [String, Object], default: () => GridIcon },
})
</script>