<template>
    <div class="flex flex-col justify-start items-start mb-6 w-full">
        <div class="relative w-full text-2xl md:text-3xl">
            <h2 class="font-black">{{ title }}</h2>
            <h3 class="absolute text-orange-500 font-extralight -bottom-5 w-full">{{ en }}</h3>
        </div>
    </div>
</template>

<script setup>

defineProps({
    title: { type: String, default: 'عنوان' },
    en: { type: String, default: 'title' },
})
</script>