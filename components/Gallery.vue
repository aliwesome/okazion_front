<template>
    <div class="w-full flex flex-col items-center relative">
        <div class="relative w-full touch-pan-x" @touchstart="onTouchStart" @touchmove="onTouchMove"
            @touchend="onTouchEnd">
            <img :src="images[activeIndex]" alt=""
                class="w-full h-72 object-cover rounded-xl transition-all duration-500">
        </div>
        <div class="flex justify-center space-x-2 rtl:space-x-reverse absolute bottom-4">
            <button v-for="(img, idx) in images" :key="idx" class="w-2 h-2 rounded-full transition-all duration-300"
                :class="[
                    activeIndex === idx
                        ? 'bg-orange-500 scale-110 shadow'
                        : 'bg-white hover:bg-orange-400'
                ]" aria-label="Go to slide" @click="activeIndex = idx" />
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

import adv2 from '../assets/files/adv/adv2.jpg'
import adv3 from '../assets/files/adv/adv3.jpg'
import adv4 from '../assets/files/adv/adv4.jpg'

const images = [adv4, adv3, adv2]
const activeIndex = ref(0)

const touchStartX = ref(null)
const touchEndX = ref(null)

function onTouchStart(e) {
    if (e.touches && e.touches.length === 1) {
        touchStartX.value = e.touches[0].clientX
    }
}

function onTouchMove(e) {
    if (e.touches && e.touches.length === 1) {
        touchEndX.value = e.touches[0].clientX
    }
}

function onTouchEnd() {
    if (touchStartX.value !== null && touchEndX.value !== null) {
        const deltaX = touchEndX.value - touchStartX.value
        // threshold for swipe
        if (Math.abs(deltaX) > 40) {
            if (deltaX < 0) {
                // swipe left, next
                activeIndex.value = (activeIndex.value + 1) % images.length
            } else if (deltaX > 0) {
                // swipe right, prev
                activeIndex.value = (activeIndex.value - 1 + images.length) % images.length
            }
        }
    }
    touchStartX.value = null
    touchEndX.value = null
}
</script>