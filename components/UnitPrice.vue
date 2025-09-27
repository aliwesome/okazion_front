<template>
    <div class="text-right">
        <h5 v-if="showTitle" class="text-xs text-gray-300 font-medium">تحلیل AI</h5>
        <h6 class="text-lg font-black">{{ price }}<span :class="spanClass + [' text-xs']">تومان</span></h6>
    </div>
</template>

<script setup>


defineProps({
    price: { type: String, default: 'مبلغ واحد' },
    showTitle: { type: Boolean, default: true },
    spanClass: {
        type: String,
        default: 'block'
    }
})
</script>