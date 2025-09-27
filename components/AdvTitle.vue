<template>
    <div class="flex flex-col gap-2 text-sm">
        <Badge v-if="showBadge" variant="black" title="تهران" />
        <div class="flex gap-2 items-start justify-start text-right">
            <HugeiconsIcon v-if="showIcon" :icon="EntranceStairsIcon" class="w-10 h-10 md:w-auto md:h-auto" />
            <div class="flex flex-col gap-1">
                <h2 class="font-bold leading-relaxed">{{ title }}</h2>
                <p v-if="showAddress" class="text-right text-base text-gray-400 leading-relaxed">
                    {{ address }}
                </p>
            </div>
        </div>
    </div>

</template>

<script setup>
import { EntranceStairsIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

import Badge from './ui/Badge.vue'

defineProps({
    title: { type: String, default: 'عنوان آگهی' },
    showIcon: { type: Boolean, default: true },
    address: { type: String, default: 'آدرس آگهی' },
    showAddress: { type: Boolean, default: true },
    showBadge: { type: Boolean, default: false },
})
</script>