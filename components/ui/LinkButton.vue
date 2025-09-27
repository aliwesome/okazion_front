<template>
  <a href="#" :class="variantClasses">
    <h6 v-if="showTitle">{{ title }}</h6>
    <HugeiconsIcon v-if="showIcon" :icon="icon" />
  </a>
</template>

<script setup>
import { ArrowRight01Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'
import { tv } from "tailwind-variants"
import { computed } from 'vue'

// Nuxt way: use defineProps with default values via destructuring and fallback
const props = defineProps({
  title: { type: String, default: 'title here' },
  icon: { type: [String, Object], default: () => ArrowRight01Icon },
  showTitle: { type: Boolean, default: true },
  showIcon: { type: Boolean, default: true },
  variant: {
    type: String,
    default: 'default',
    validator: v => ['default', 'secondary', 'destructive', 'outline', 'success', 'warning', 'info'].includes(v)
  },
  direction: {
    type: String,
    default: 'left',
    validator: v => ['left', 'right'].includes(v)
  }
})

// Define linkButton variants using tailwind-variants
const linkButtonVariants = tv({
  base: [
    "flex items-center gap-2 w-fit rounded-xl text-sm p-3",
    "transition-colors",
  ],
  variants: {
    variant: {
      default: "bg-orange-500 border-transparent text-primary-foreground hover:bg-orange-600",
      black: "bg-black text-primary-foreground hover:bg-orange-500",
      pdf: "bg-rose-500 border-transparent text-primary-foreground hover:bg-rose-600",
      secondary: "border-transparent bg-secondary text-secondary-foreground hover:bg-secondary/80",
      destructive: "border-transparent bg-destructive text-destructive-foreground hover:bg-destructive/80",
      outline: "border border-gray-200 text-black hover:text-orange-500 transition-all",
      success: "border-transparent bg-green-500 text-white hover:bg-green-600",
      warning: "border-transparent bg-yellow-500 text-white hover:bg-yellow-600",
      info: "border-transparent bg-blue-500 text-white hover:bg-blue-600",
    },
    direction: {
      left: "flex-row",
      right: "flex-row-reverse"
    },
  }
})

const variantClasses = computed(() => linkButtonVariants({
  variant: props.variant,
  direction: props.direction
}))
</script>