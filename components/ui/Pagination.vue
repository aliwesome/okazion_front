<template>
    <nav class="w-full flex justify-center items-center gap-2 my-6">
        <!-- Left Arrow -->
        <button :disabled="currentPage === 1"
            class="w-9 h-9 flex items-center justify-center border border-gray-200 rounded-lg transition-colors bg-white hover:bg-orange-50 disabled:opacity-50 disabled:cursor-not-allowed"
            aria-label="Previous page" @click="goToPage(currentPage - 1)">
            <HugeiconsIcon :icon="ArrowRight01Icon" class="w-5 h-5" />
        </button>

        <!-- Page Numbers -->
        <button v-for="page in pages" :key="page"
            class="w-9 h-9 flex items-center justify-center border rounded-lg transition-colors" :class="[
                currentPage === page
                    ? 'bg-black text-white border-black'
                    : 'bg-white text-gray-800 border-gray-200 hover:bg-orange-50'
            ]" @click="goToPage(page)">
            {{ page }}
        </button>

        <!-- Right Arrow -->
        <button :disabled="currentPage === pageCount"
            class="w-9 h-9 flex items-center justify-center border border-gray-200 rounded-lg transition-colors bg-white hover:bg-orange-50 disabled:opacity-50 disabled:cursor-not-allowed"
            aria-label="Next page" @click="goToPage(currentPage + 1)">
            <HugeiconsIcon :icon="ArrowLeft01Icon" class="w-5 h-5" />
        </button>
    </nav>
</template>

<script setup>
import { ArrowLeft01Icon, ArrowRight01Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'
import { ref, computed } from 'vue'

const props = defineProps({
    modelValue: { type: Number, default: 1 },
    pageCount: { type: Number, default: 5 }
})
const emit = defineEmits(['update:modelValue'])

const currentPage = ref(props.modelValue)

const pages = computed(() => {
    // Show all pages if <= 7, else show first, last, current, and neighbors (simple version)
    if (props.pageCount <= 7) {
        return Array.from({ length: props.pageCount }, (_, i) => i + 1)
    }
    // For more advanced ellipsis logic, you can expand here
    // For now, just show 1..current-1,current,current+1..last
    const arr = [1]
    if (currentPage.value > 3) arr.push('...')
    for (let i = Math.max(2, currentPage.value - 1); i <= Math.min(props.pageCount - 1, currentPage.value + 1); i++) {
        arr.push(i)
    }
    if (currentPage.value < props.pageCount - 2) arr.push('...')
    arr.push(props.pageCount)
    return arr
})

function goToPage(page) {
    if (typeof page !== 'number' || page < 1 || page > props.pageCount) return
    currentPage.value = page
    emit('update:modelValue', page)
}
</script>