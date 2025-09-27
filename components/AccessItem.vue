<template>
    <div class="flex flex-col items-center justify-center gap-y-1 p-4">
        <HugeiconsIcon :icon="icon" />
        <div class="flex flex-col gap-1 text-center">
            <h5>{{ title }}</h5>
            <h6 class="text-gray-400 text-sm">{{ distance }}</h6>
        </div>
    </div>
</template>

<script setup>
import { BankIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'


defineProps({
    title: { type: String, default: 'عنوان' },
    distance: { type: String, default: 'مسافت' },
    icon: { type: [String, Object], default: () => BankIcon },

})

</script>