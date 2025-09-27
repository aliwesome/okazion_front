<template>
    <div class="flex items-center gap-2">
        <span class="w-2 h-2 bg-orange-500 block rounded-[2px]" />
        <h3 class="text-base text-black font-normal">{{ title }}</h3>
    </div>
</template>

<script setup>
defineProps({
  title: { type: String, default: 'عنوان کارت ها' },
})
</script>