<template>
    <div class="flex flex-row-reverse items-center gap-0.5">
        <span v-for="star in 5" :key="star" class="inline-flex" :aria-label="`امتیاز ${star}`">
            <svg :class="star <= rate ? 'text-orange-500' : 'text-gray-300'" class="w-4 h-4 transition-colors"
                fill="currentColor" viewBox="0 0 20 20">
                <path
                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.286 3.967a1 1 0 00.95.69h4.175c.969 0 1.371 1.24.588 1.81l-3.38 2.455a1 1 0 00-.364 1.118l1.287 3.966c.3.922-.755 1.688-1.54 1.118l-3.38-2.455a1 1 0 00-1.175 0l-3.38 2.455c-.784.57-1.838-.196-1.54-1.118l1.287-3.966a1 1 0 00-.364-1.118L2.05 9.394c-.783-.57-.38-1.81.588-1.81h4.175a1 1 0 00.95-.69l1.286-3.967z" />
            </svg>
        </span>
    </div>
</template>

<script setup>
defineProps({
    rate: {
        type: Number,
        default: 3
    }
})
</script>