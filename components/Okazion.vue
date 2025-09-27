<template>
    <div class="flex flex-col justify-center items-center w-full gap-10 md:gap-12">
        <div class="relative w-fit text-5xl md:text-6xl">
            <h2 :class="faClass + [' font-black rotate-3']">اُکازیون</h2>
            <h3 class="absolute text-orange-500 font-extralight -rotate-3 -bottom-8">Okazion</h3>
        </div>
        <!-- slogan -->
        <p v-if="showSlogan" class="text-xl md:text-2xl font-extralight text-black">مهندسی ارزش ملک؛ واقعی تر از هر آگهی
        </p>
    </div>
</template>


<script setup>

defineProps({
    showSlogan: { type: Boolean, default: false },
    faClass: {
        type: String,
        default: 'text-black'
    }
})
</script>
