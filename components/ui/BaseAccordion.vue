<template>
    <div class="w-full">
        <div class="w-full">
            <button
                class="flex items-center justify-between w-full px-4 py-5 rounded-xl border border-gray-200 hover:opacity-75 transition-colors focus:outline-none"
                @click="toggleAccordion">
                <h4 :class="isOpen ? 'text-orange-500' : 'text-gray-800'">{{ question }}</h4>
                <span class="ml-2 transition-transform duration-200"
                    :class="[{ 'rotate-180': isOpen }, isOpen ? 'text-orange-500' : 'text-gray-500']">
                    <HugeiconsIcon :icon="ArrowDown01Icon" class="w-5 h-5" />
                </span>
            </button>
            <div v-show="isOpen"
                class="w-full text-right mt-4 px-4 py-3 text-gray-700 bg-gray-50 transition-all duration-200 border border-gray-200 rounded-xl">
                {{ answer }}
            </div>
        </div>
    </div>
</template>

<script setup>
import { ArrowDown01Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'
import { ref, onMounted, onBeforeUnmount } from 'vue'

defineProps({
    question: { type: String, default: 'سوال' },
    answer: { type: String, default: 'جواب' },
})

const isOpen = ref(false)
const accordionId = Symbol('accordionId')

// Simple event bus for accordion coordination
const ACCORDION_EVENT = '__base_accordion_open__'

function onAccordionOpen(event) {
    if (event.detail && event.detail !== accordionId) {
        isOpen.value = false
    }
}

function toggleAccordion() {
    if (!isOpen.value) {
        // Opening: notify others to close
        window.dispatchEvent(new CustomEvent(ACCORDION_EVENT, { detail: accordionId }))
    }
    isOpen.value = !isOpen.value
}

onMounted(() => {
    window.addEventListener(ACCORDION_EVENT, onAccordionOpen)
})
onBeforeUnmount(() => {
    window.removeEventListener(ACCORDION_EVENT, onAccordionOpen)
})
</script>