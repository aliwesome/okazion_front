<template>
    <div class="flex flex-col gap-3 h-full">
        <label v-if="showLabel" class="text-sm" :for="text"> {{ label }}</label>
        <div class="base-select-root relative flex items-center bg-white border border-gray-200 h-full rounded-xl px-3 cursor-pointer select-none"
            tabindex="0" @click="isOpen = !isOpen">
            <span class="flex-1 text-sm" :class="selectedOption ? 'text-gray-900' : 'text-gray-400'">
                {{ selectedOption ? selectedOption.label : placeholder }}
            </span>
            <HugeiconsIcon :icon="ArrowDown01Icon" class="w-5 h-5 ml-2 text-gray-400 transition-transform duration-200"
                :class="{ 'rotate-180': isOpen }" />
            <ul v-if="isOpen"
                class="absolute text-sm left-0 top-full mt-2 w-full bg-white border border-gray-200 rounded-lg shadow-lg z-10 max-h-60 overflow-auto">
                <li v-for="option in options" :key="option.value"
                    class="px-4 py-2 cursor-pointer hover:bg-orange-50 transition-all"
                    :class="{ 'bg-orange-50 text-orange-500': isActiveOption(option) }"
                    @click.stop="selectOption(option)">
                    <span v-if="option.flagClass" class="fi mr-2 rounded" :class="option.flagClass"
                        style="width:20px;height:20px;display:inline-block;vertical-align:middle;" />
                    <HugeiconsIcon v-if="option.icon" :icon="option.icon"
                        class="w-4 h-4 mr-2 inline-block align-middle" />
                    <span class="align-middle">{{ option.label }}</span>
                </li>
            </ul>
        </div>
    </div>

</template>

<script setup>
import { ArrowDown01Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'
import { ref, computed, onMounted, watch } from 'vue'

const props = defineProps({
    label: { type: String, default: 'عنوان فرم' },
    showLabel: { type: Boolean, default: false },
    modelValue: {
        type: [String, Number, Object],
        default: null
    },
    options: { type: Array, required: true },
    placeholder: { type: String, default: 'عنوان' }
})
const emit = defineEmits(['update:modelValue'])

const isOpen = ref(false)
const internalValue = ref(props.modelValue)

watch(() => props.modelValue, (val) => {
    internalValue.value = val
})

const selectedOption = computed(() =>
    Array.isArray(props.options)
        ? props.options.find(opt => opt.value === internalValue.value) || null
        : null
)
const isActiveOption = option => option.value === internalValue.value

function selectOption(option) {
    internalValue.value = option.value
    emit('update:modelValue', option.value)
    isOpen.value = false
}

onMounted(() => {
    document.addEventListener('click', e => {
        if (!e.target.closest('.base-select-root')) isOpen.value = false
    })
})
</script>

<style scoped>
.base-select-root {
    min-width: 160px;
}

.rotate-180 {
    transform: rotate(180deg);
}
</style>