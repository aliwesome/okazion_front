<template>
    <section class="flex flex-col justify-center items-center gap-y-4 md:gap-y-8 py-4 md:py-6 relative">
        <div class="relative flex flex-col items-center gap-y-6 md:gap-y-10">
            <!-- Vertical line (before) in center, taller only in md mode -->
            <div
                class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 h-[calc(100%+64px)] md:h-[calc(100%+128px)] w-56 md:w-80 bg-orange-500/5 rounded-xl -z-10" />
            <!-- icon -->
            <div class="p-2 rounded-lg bg-orange-500/15 text-orange-500 w-fit">
                <HugeiconsIcon :icon="Agreement02Icon" class="w-9 h-9" />
            </div>
            <!-- content -->
            <ul class="flex flex-col items-center gap-y-6">
                <li>
                    <h2 class="text-3xl md:text-5xl font-black">همکاری با اُکازیون </h2>
                </li>
                <li>
                    <p class="text-xl md:text-3xl font-extralight">در دسترس برای همه کارشناسان</p>
                </li>
                <li class="w-full">
                    <ul class="flex items-center gap-x-6 text-center">
                        <li class="flex-shrink w-full">
                            <h6>مشاورین املاک</h6>
                        </li>
                        <li> <span class="block w-2 h-2 rounded-full bg-orange-500" /></li>
                        <li class="flex-shrink w-full">
                            <h6>سازمان ها</h6>
                        </li>
                        <li> <span class="block w-2 h-2 rounded-full bg-orange-500" /></li>
                        <li class="flex-shrink w-full">
                            <h6>کارشناسان رسمی</h6>
                        </li>
                    </ul>
                </li>
            </ul>
            <!-- link -->
            <div>
                <LinkButton :icon="ArrowRight01Icon" title="ثبت نام" direction="right" />
            </div>
        </div>
        <!-- images -->
        <div class="hidden md:block">
            <!-- img1: Move higher and more to the left on tablet, randomly rotate -->
            <img :src="img1" alt="" class="absolute rounded-xl w-32 h-32 top-0 left-4
                       md:w-40 md:h-40 md:top-0 md:left-0
                       lg:top-8 lg:left-16
                       rotate-3
                       " style="z-index:1;">
            <!-- img2: Move further down and more to the right on tablet, randomly rotate -->
            <img :src="img2" alt="" class="absolute rounded-xl w-28 h-28 bottom-8 right-8
                       md:w-36 md:h-36 md:bottom-4 md:right-8
                       lg:bottom-16 lg:right-24
                       -rotate-6
                       " style="z-index:2;">
            <!-- img3: Move closer to center vertically and more to the right on tablet, randomly rotate -->
            <img :src="img3" alt="" class="absolute rounded-xl w-24 h-24 top-1/2 right-0
                       md:w-32 md:h-32 md:top-1/2 md:right-4
                       lg:top-1/3 lg:right-12
                       rotate-12
                       " style="z-index:1;">
            <!-- img4: Move up and more to the left on tablet, randomly rotate -->
            <img :src="img4" alt="" class="absolute rounded-xl w-20 h-20 bottom-0 left-1/2 -translate-x-1/2
                       md:w-28 md:h-28 md:bottom-4 md:left-1/4 md:-translate-x-0
                       lg:bottom-8 lg:left-1/4
                       -rotate-2
                       " style="z-index:2;">
            <!-- img5: New image, top right corner, randomly rotate -->
            <img :src="img2" alt="" class="absolute rounded-xl w-16 h-16 top-4 right-4
                       md:w-20 md:h-20 md:top-2 md:right-2
                       lg:top-8 lg:right-80
                       rotate-6
                       " style="z-index:1;">
            <!-- img6: New image, bottom left corner, randomly rotate -->
            <img :src="img4" alt="" class="absolute rounded-xl w-16 h-16 bottom-4 left-4
                       md:w-20 md:h-20 md:bottom-2 md:left-2
                       lg:bottom-8 lg:left-12
                       -rotate-12
                       " style="z-index:2;">
        </div>
    </section>
</template>

<script setup>
import { Agreement02Icon, ArrowRight01Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

import LinkButton from '../../components/ui/LinkButton'
import img1 from '../assets/files/images/img1.png'
import img2 from '../assets/files/images/img2.png'
import img3 from '../assets/files/images/img3.png'
import img4 from '../assets/files/images/img4.png'

</script>