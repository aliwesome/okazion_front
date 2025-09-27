<template>
    <div class="flex flex-col gap-3 text-right ">
        <label v-if="showLabel" class="text-sm" :for="text"> {{ label }}</label>
        <div class="flex flex-col gap-2">
            <div :class="variantClasses">
                <textarea :rows="rows" :placeholder="placeholder" :maxlength="maxlength"
                    class="text-sm bg-transparent w-full px-1 focus-visible:outline-0 resize-none" />
                <HugeiconsIcon v-if="showIcon" :icon="icon" class="w-7 h-7" />
            </div>
            <!-- Error Message -->
            <p v-if="showError || error" class="text-xs text-red-500">{{ errorTitle }}</p>
        </div>
    </div>
</template>

<script setup>
import { User02Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'
import { tv } from "tailwind-variants"
import { computed } from 'vue'

const props = defineProps({
    label: { type: String, default: 'عنوان فرم' },
    showLabel: { type: Boolean, default: true },
    placeholder: { type: String, default: 'متن راهنما' },
    icon: { type: [String, Object], default: () => User02Icon },
    showIcon: { type: Boolean, default: false },
    errorTitle: { type: String, default: 'فیلد اجباری است' },
    showError: { type: Boolean, default: false },
    maxlength: { type: String, default: '200' },
    rows: { type: String, default: '4' },
    variant: {
        type: String,
        default: 'default',
        validator: v => ['default', 'error'].includes(v)
    }
})

// Define textarea variants using tailwind-variants
const textareaVariants = tv({
    base: [
        "inline-flex items-start justify-between border border-gray-200 rounded-xl p-4",
    ],
    variants: {
        variant: {
            default: "bg-white-500",
            error: "border-transparent bg-red-500/10 border-red-500 text-red-500"
        }
    }
})

const variantClasses = computed(() => textareaVariants({
    variant: props.variant
}))
</script>