<template>
    <div :class="variantClasses">
        <!-- icon image for each variant -->
        <div class="flex items-center justify-center w-8 h-8">
            <!-- Use require for static asset resolution -->
            <img v-if="showImage" :src="imgSrc" alt="divar icon" class="w-5 h-5">
        </div>
        <div class="text-right">
            <h5 class="text-xs font-medium">{{ title }}</h5>
            <div class="flex items-center justify-between gap-2">
                <h6 class="text-black text-xs font-medium">{{ subtitle }}</h6>
                <HugeiconsIcon v-if="showIcon" :icon="icon" class="text-green-600" />
            </div>
        </div>
    </div>
</template>

<script setup>
import { TradeUpIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'
import { tv } from "tailwind-variants"
import { computed } from 'vue'

// Nuxt way: use defineProps with default values via destructuring and fallback
const props = defineProps({
    title: { type: String, default: 'بج خور' },
    subtitle: { type: String, default: 'بج خور' },
    icon: { type: [String, Object], default: () => TradeUpIcon },
    showIcon: { type: Boolean, default: true },
    imgSrc: { type: String, required: true },
    showImage: { type: Boolean, default: true },
    variant: {
        type: String,
        default: 'silver',
        validator: v => ['silver', 'gold', 'champion', 'platinum', 'diamond'].includes(v)
    }
})

// Define linkButton variants using tailwind-variants
const AdvbadgeVariants = tv({
    base: [
        "flex items-center rounded-xl p-2 h-full",
    ],
    variants: {
        variant: {
            silver: "bg-slate-500/5 text-slate-400",
            gold: "bg-yellow-700/5  text-yellow-500",
            champion: "bg-rose-600/5  text-rose-500",
            platinum: "bg-sky-500/5  text-sky-500",
            diamond: "bg-pink-500/5  text-pink-500",
        }
    }
})

const variantClasses = computed(() => AdvbadgeVariants({
    variant: props.variant
}))
</script>