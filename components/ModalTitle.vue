<template>
    <div class="flex items-center justify-between border-b border-b-gray-200 pb-4">
        <div>
            <Logo v-if="showLogo" />
            <h2 v-if="showTitle" class="text-base text-black font-medium">{{ title }}</h2>
        </div>
        <Button :show-title="false" variant="outline" :icon="CancelSquareIcon"/>
    </div>
</template>

<script setup>
import { CancelSquareIcon } from "@hugeicons/core-free-icons";

import Logo from './Logo'
import Button from './ui/Button'

defineProps({
    showLogo: { type: Boolean, default: false },
    title: { type: String, default: 'عنوان در اینجا' },
    showTitle: { type: Boolean, default: false },
})
</script>