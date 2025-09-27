<template>
    <div class="flex items-center gap-x-2 border rounded-lg border-gray-200 p-3">
        <HugeiconsIcon :icon="ViewIcon" />
        <span class="text-gray-200">|</span>
        <h6>{{ number }}</h6>
    </div>
</template>

<script setup>
import { ViewIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

defineProps({
    number: { type: String, default: '0' }
})

</script>