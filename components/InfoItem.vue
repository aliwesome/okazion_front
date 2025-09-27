<template>
    <div class="flex items-center gap-4 border border-gray-200 rounded-xl p-4">
        <!-- icon -->
        <div class="p-2 rounded-lg bg-orange-500/15 text-orange-500">
            <span v-if="showNum" class="text-orange-500 font-black px-2 min-w-8 block text-center">{{ number }}</span>
            <HugeiconsIcon v-if="showIcon" :icon="icon" />
        </div>
        <!-- content -->
        <div>
            <h5 class="text-sm font-semibold text-black">{{ title }}</h5>
            <h6 class="text-base text-gray-400 font-normal">{{ subtitle }}</h6>
        </div>
    </div>
</template>

<script setup>
import { GridIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

defineProps({
    title: { type: String, default: 'عنوان' },
    subtitle: { type: String, default: 'ساب تایتل' },
    number: { type: String, default: '1' },
    showNum: { type: Boolean, default: false },
    showIcon: { type: Boolean, default: true },
    icon: { type: [String, Object], default: () => GridIcon },
})
</script>