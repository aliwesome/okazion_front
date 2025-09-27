<template>
    <label class="relative flex items-center cursor-pointer select-none">
        <input type="checkbox" class="sr-only peer" :checked="modelValue" role="switch" :aria-checked="modelValue"
            @change="$emit('update:modelValue', $event.target.checked)">
        <!-- Track -->
        <span class="block w-12 h-7 rounded-full transition-colors duration-300"
            :class="modelValue ? 'bg-green-500' : 'bg-gray-300'" />
        <!-- Thumb -->
        <span
            class="absolute left-0.5 top-0.5 w-6 h-6 rounded-full bg-white border border-gray-200 shadow-md transition-all duration-300"
            :class="modelValue ? 'translate-x-5 border-green-500' : 'translate-x-0 border-gray-300'"
            style="will-change: transform;" />
        <!-- Optional icon or checkmark inside thumb -->
        <span class="absolute left-1.5 top-1.5 text-green-500 transition-opacity duration-300 pointer-events-none"
            :class="modelValue ? 'opacity-100' : 'opacity-0'">
            <svg width="16" height="16" fill="none" viewBox="0 0 16 16">
                <path d="M4 8.5l3 3 5-5" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                    stroke-linejoin="round" />
            </svg>
        </span>
    </label>
</template>

<script setup>
defineProps({
    modelValue: { type: Boolean, default: false }
})
defineEmits(['update:modelValue'])
</script>