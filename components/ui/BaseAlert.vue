<template>
    <p :class="variantClasses">
        {{ title }}
    </p>
</template>

<script setup>

import { tv } from "tailwind-variants"
import { computed } from 'vue'

// Nuxt way: use defineProps with default values via destructuring and fallback
const props = defineProps({
    title: { type: String, default: 'title here' },
    variant: {
        type: String,
        default: 'default',
        validator: v => ['default', 'success', 'warning', 'info'].includes(v)
    }
})

// Define linkButton variants using tailwind-variants
const linkButtonVariants = tv({
    base: [
        "text-center rounded-xl p-4 text-sm",
    ],
    variants: {
        variant: {
            default: "bg-orange-500/15 text-orange-500 border-transparent",
            success: "border-transparent bg-green-500/15 text-green-500 ",
            warning: "border-transparent bg-yellow-500/15 text-yellow-500 ",
            info: "border-transparent bg-blue-500/15 text-blue-500 ",
            neutral: "border-transparent bg-black/5 text-black ",
        }
    }
})

const variantClasses = computed(() => linkButtonVariants({
    variant: props.variant,
    direction: props.direction
}))
</script>