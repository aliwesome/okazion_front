<template>
    <div class="flex items-center justify-between">
        <h5 class="font-semibold">{{ title }}</h5>
        <div class="flex items-center gap-x-2">
            <p class="text-sm md:text-base">بازگشت به خانه</p>
            <LinkButton :show-title="false" :icon="ArrowLeft01Icon" variant="outline" />
        </div>
    </div>
</template>

<script setup>
import { ArrowLeft01Icon } from '@hugeicons/core-free-icons'

import LinkButton from './ui/LinkButton.vue'

defineProps({
    title: { type: String, default: 'عنوان' },

})
</script>