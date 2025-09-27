<template>
    <a href="#" class="rounded-xl relative block h-72 md:h-auto">
        <img :src="imgSrc" alt="" class="rounded-xl h-full">
        <!-- content -->
        <div class="md:min-w-[435px] w-fit absolute bottom-6 md:top-auto right-6 left-6 rounded-lg backdrop-blur-sm
 bg-white/75 p-6">
            <BlogItem title="چرا هزینه های ملک در منطقه ۲۱ افزایشی است؟" />
        </div>
    </a>
</template>

<script setup>
import BlogItem from './BlogItem'
defineProps({
    imgSrc: { type: String, required: true },
})

</script>