<template>
    <div class="flex flex-col gap-3 text-right ">
        <label v-if="showLabel" class="text-sm" :for="text"> {{ label }}</label>
        <div class="flex flex-col gap-2 bg-white">
            <div :class="variantClasses">
                <img v-if="showImage" :src="imgSrc" alt="divar icon" class="w-8 h-8">
                <input :id="text" :type="type" :name="text" :placeholder="placeholder" :maxlength="maxlength"
                    :class="inputClass + [' text-sm bg-transparent w-full px-1 focus-visible:outline-0']">
                <button v-if="showButton"
                    class="hover:text-orange-500 transition-all border border-gray-300 p-1 rounded-md bg-gray-50 md:border-none md:p-0 md:bg-transparent">
                    <HugeiconsIcon :icon="icon" class="w-8 h-8" />
                </button>
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
    type: { type: String, default: 'text' },
    for: { type: String, default: 'text' },
    name: { type: String, default: 'text' },
    id: { type: String, default: 'text' },
    placeholder: { type: String, default: 'متن راهنما' },
    imgSrc: { type: String, required: true },
    showImage: { type: Boolean, default: false },
    icon: { type: [String, Object], default: () => User02Icon },
    showIcon: { type: Boolean, default: false },
    errorTitle: { type: String, default: 'فیلد اجباری است' },
    showError: { type: Boolean, default: false },
    showButton: { type: Boolean, default: false },
    maxlength: { type: String, default: '200' },
    inputClass: {
        type: String,
        default: 'py-5'
    },
    variant: {
        type: String,
        default: 'default',
        validator: v => ['default', 'error'].includes(v)
    }
})

// Define input variants using tailwind-variants
const inputVariants = tv({
    base: [
        "inline-flex items-center justify-between border border-gray-200 rounded-xl px-4",
    ],
    variants: {
        variant: {
            default: "bg-white-500",
            error: "border-transparent bg-red-500/10 border-red-500 text-red-500"
        }
    }
})

const variantClasses = computed(() => inputVariants({
    variant: props.variant
}))
</script>