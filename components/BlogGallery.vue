<template>
    <div class="w-full flex flex-col items-center">
        <div class="relative w-full flex flex-col items-center">
            <!-- Mobile/Tablet Arrows -->
            <button
                class="absolute left-2 top-1/2 -translate-y-1/2 z-20 flex md:hidden items-center justify-center w-10 h-10 rounded-full bg-white/80 shadow hover:bg-white"
                aria-label="قبلی" :disabled="slides.length <= 1" style="transition: background 0.2s;" @click="goToPrev">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 " fill="none" viewBox="0 0 24 24"
                    stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                </svg>
            </button>
            <button
                class="absolute right-2 top-1/2 -translate-y-1/2 z-20 flex md:hidden items-center justify-center w-10 h-10 rounded-full bg-white/80 shadow hover:bg-white"
                aria-label="بعدی" :disabled="slides.length <= 1" style="transition: background 0.2s;" @click="goToNext">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24"
                    stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                </svg>
            </button>
            <ul ref="sliderList"
                class="w-full flex flex-nowrap md:gap-x-6 overflow-x-auto md:overflow-visible justify-center touch-pan-x scrollbar-hide"
                style="scroll-behavior: smooth;" @touchstart="onTouchStart" @touchmove="onTouchMove"
                @touchend="onTouchEnd">
                <li v-for="(slide, idx) in centeredSlides" :key="slide.originalIndex"
                    class="shrink-0 flex items-center justify-center w-full md:w-auto" :style="{
                        order: idx === centerIndex ? 1 : idx < centerIndex ? 0 : 2,
                        transition: 'transform 0.5s cubic-bezier(.4, 0, .2, 1)'
                    }" :tabindex="activeIndex === slide.originalIndex ? -1 : 0"
                    :aria-disabled="activeIndex === slide.originalIndex" style="cursor: pointer;"
                    @click="handleSlideClick(slide.originalIndex)">
                    <component :is="activeIndex === slide.originalIndex ? 'a' : 'div'"
                        :href="activeIndex === slide.originalIndex ? '#' : undefined"
                        class="w-full md:w-[800px] transition-all duration-500"
                        :class="activeIndex === slide.originalIndex ? 'grayscale-0 z-10' : 'grayscale opacity-70 z-0 pointer-events-none'"
                        :tabindex="activeIndex === slide.originalIndex ? 0 : -1"
                        :aria-disabled="activeIndex !== slide.originalIndex" style="display: block;">
                        <BlogSliderItem :title="slide.title" :img-src="slide.img" />
                    </component>
                </li>
            </ul>
        </div>
        <!-- Dots: only show on md and up -->
        <div class="gap-x-2 mt-4 hidden md:flex">
            <button v-for="(slide, idx) in slides" :key="'dot-' + idx"
                class="w-2 h-2 rounded-full transition-colors duration-300"
                :class="activeIndex === idx ? 'bg-orange-500' : 'bg-gray-300'" aria-label="انتخاب اسلاید"
                @click="goToSlide(idx)" />
        </div>
    </div>
</template>

<script setup>
import { ref, computed, nextTick } from 'vue'

import img1 from '../assets/files/blog/img1.jpg'
import img2 from '../assets/files/blog/img2.jpg'
import img3 from '../assets/files/blog/img3.jpg'

import BlogSliderItem from './BlogSliderItem'

const slides = [
    {
        title: "بالارفتن اجاره بهای خانه در تهران",
        img: img1,
    },
    {
        title: "بررسی قیمتی املاک منطقه ۲۲ تهران",
        img: img2,
    },
    {
        title: "چرا هزینه های ملک در منطقه ۲۱ افزایشی است؟",
        img: img3,
    }
]

// Set default slide to the second slide (index 1)
const activeIndex = ref(1)

// --- Swipe logic for mobile ---
const sliderList = ref(null)
let touchStartX = 0
let touchEndX = 0
let isSwiping = false

function onTouchStart(e) {
    if (window.innerWidth >= 768) return // Only on mobile
    isSwiping = true
    touchStartX = e.touches[0].clientX
}

function onTouchMove(e) {
    if (!isSwiping || window.innerWidth >= 768) return
    touchEndX = e.touches[0].clientX
}

function onTouchEnd() {
    if (!isSwiping || window.innerWidth >= 768) return
    const deltaX = touchEndX - touchStartX
    if (Math.abs(deltaX) > 50) {
        if (deltaX < 0) {
            // swipe left, next
            goToSlide((activeIndex.value + 1) % slides.length)
        } else {
            // swipe right, prev
            goToSlide((activeIndex.value - 1 + slides.length) % slides.length)
        }
    }
    isSwiping = false
    touchStartX = 0
    touchEndX = 0
}

// Smoothly go to a slide (for dots and swipe)
function goToSlide(idx) {
    if (activeIndex.value === idx) return
    activeIndex.value = idx
    // Optionally, scroll into view for mobile
    nextTick(() => {
        if (sliderList.value && window.innerWidth < 768) {
            const activeLi = sliderList.value.querySelector('li:nth-child(2)')
            if (activeLi) {
                activeLi.scrollIntoView({ behavior: 'smooth', inline: 'center', block: 'nearest' })
            }
        }
    })
}

// Arrow controls for mobile/tablet
function goToPrev() {
    goToSlide((activeIndex.value - 1 + slides.length) % slides.length)
}
function goToNext() {
    goToSlide((activeIndex.value + 1) % slides.length)
}

// Handle click on slide: if not active, go to that slide
function handleSlideClick(idx) {
    if (activeIndex.value !== idx) {
        goToSlide(idx)
    }
}

// Compute slides so that the active one is always in the center
const centeredSlides = computed(() => {
    // For 3 slides, always show all, but center the active one
    // For more slides, you could show prev, active, next
    // We'll rotate the array so activeIndex is in the center
    const n = slides.length
    if (n <= 1) return slides.map((s, i) => ({ ...s, originalIndex: i }))
    // For 3 slides, order: [prev, active, next]
    const prev = (activeIndex.value - 1 + n) % n
    const next = (activeIndex.value + 1) % n
    return [
        { ...slides[prev], originalIndex: prev },
        { ...slides[activeIndex.value], originalIndex: activeIndex.value },
        { ...slides[next], originalIndex: next }
    ]
})
const centerIndex = 1 // always the middle in centeredSlides
</script>

<style>
/* Hide scrollbar for all browsers */
.scrollbar-hide {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.scrollbar-hide::-webkit-scrollbar {
    display: none;
    /* Chrome, Safari, Opera */
}
</style>