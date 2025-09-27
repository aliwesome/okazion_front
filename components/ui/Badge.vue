<template>
  <div :class="variantClasses">
    <h6 class="text-sm font-semibold">{{ title }}</h6>
  </div>
</template>

<script setup>
import { tv } from "tailwind-variants"
import { computed } from 'vue'

const props = defineProps({
  title: { type: String, default: 'بج خور' },
  variant: { 
    type: String, 
    default: 'default', 
    validator: v => ['default', 'secondary'].includes(v)
  }
})


const badgeVariants = tv({
  base: [
    "flex items-center w-fit rounded-lg p-2",
  ],
  variants: {
    variant: {
      default: "bg-orange-500/25 text-orange-500",
      black: "bg-black/10  text-black",
    }
  }
})

const variantClasses = computed(() => badgeVariants({
  variant: props.variant
}))
</script>