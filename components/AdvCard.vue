<template>
    <div class="border border-gray-100 bg-white rounded-xl w-full md:w-80">
        <!-- top -->
        <div>
            <!-- image + ad title -->
            <div class="relative">
                <img :src="imgSrc" alt="" class="w-full h-32 object-cover rounded-xl">
                <div class="p-4 absolute top-0 z-10">
                    <AdvTitle title="۱۰۰ متر دو خواب شهرک راه آهن/ ۲ ساله سروستان/کوهک" :show-icon="false"
                        :show-address="false" :show-badge="true" class="pl-2" />
                </div>
                <div
                    class="after:content-[''] after:absolute after:inset-0 after:bg-gradient-to-t after:from-white after:to-white/40" />
            </div>
            <!-- Ads badges -->
            <ul class="flex  items-stretch flex-wrap gap-2 px-4">
                <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                    <AdvBadge title="رشد منطقه" subtitle="۶۰% نسبت به ۱۴۰۳" variant="silver" :img-src="silver" />
                </li>
                <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                    <AdvBadge title="تحلیل AI" subtitle="اُکازیون" variant="champion" :show-icon="false"
                        :img-src="champion" />
                </li>
                <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                    <AdvBadge title="قیمت واحد" subtitle="معقول" variant="gold" :show-icon="false" :img-src="gold" />
                </li>
                <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                    <AdvBadge title="موقعیت ملک" subtitle="عالی" variant="platinum" :show-icon="false"
                        :img-src="platinum" />
                </li>
                <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                    <AdvBadge title="ارزش منطقه" subtitle="بالا" variant="diamond" :show-icon="false"
                        :img-src="diamond" />
                </li>

            </ul>
        </div>
        <!-- bottom -->
        <div class="flex items-center justify-between p-4">
            <UnitPrice price="۱۲.۵۰۰.۰۰۰.۰۰۰" span-class="inline-block" />
            <LinkButton title="مشاهده" class="text-sm" :icon="CircleArrowLeft01Icon" variant="black" />
        </div>
    </div>
</template>

<script setup>
import { CircleArrowLeft01Icon } from '@hugeicons/core-free-icons'

import champion from '../assets/files/images/champion.svg'
import diamond from '../assets/files/images/diamond.svg'
import gold from '../assets/files/images/gold.svg'
import platinum from '../assets/files/images/platinum.svg'
import silver from '../assets/files/images/silver.svg'

import AdvTitle from './AdvTitle.vue'
import AdvBadge from './ui/AdvBadge.vue'
import LinkButton from './ui/LinkButton.vue'
import UnitPrice from './UnitPrice.vue'
defineProps({
    imgSrc: { type: String, required: true },
})

</script>