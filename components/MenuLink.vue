<template>
    <a href="#" class="flex items-center justify-between py-4 border-b border-b-gray-200 text-black hover:text-orange-500 transition-all">
        <h3 class="font-medium text-sm">{{ title }}</h3>
        <HugeiconsIcon :icon="ArrowLeft01Icon" />
    </a>
</template>

<script setup>
import { ArrowLeft01Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

defineProps({
  title: { type: String, default: 'عنوان لینک' },
})

</script>