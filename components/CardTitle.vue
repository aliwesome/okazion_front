<template>
  <div class="flex items-center gap-2 font-normal">
    <HugeiconsIcon :icon="icon" />
    <h3 class="text-base text-black">{{ title }}</h3>
  </div>
</template>

<script setup>
import { AiMagicIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

defineProps({
  title: { type: String, default: 'title here' },
  icon: { type: [String, Object], default: () => AiMagicIcon },
})
</script>