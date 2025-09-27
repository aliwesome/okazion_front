<template>
        <h6 class="text-lg font-black">{{ price }}<span :class="spanClass + [' text-xs']">تومان</span></h6>
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