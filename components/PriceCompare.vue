<template>
    <div class="flex flex-col gap-4 h-full">
        <div class="flex items-center justify-between">
            <CardTitle title="مقایسه قیمت" />
            <!-- Actions & badge -->
            <ul class="flex  items-stretch  gap-2">
                <li>
                    <Badge title="فروش" class="h-full" />
                </li>
                <li>
                    <LinkButton :show-title="false" :icon="Pdf01Icon" variant="pdf" />
                </li>
                <li>
                    <LinkButton :show-title="false" :icon="Share08Icon" variant="outline" />
                </li>
            </ul>
        </div>
        <!-- Cmpare -->
        <div class="relative grid grid-cols-2 gap-4 md:gap-6 h-full">
            <!-- Okazion -->
            <div class="flex flex-col justify-between gap-y-8 md:gap-y-16 p-6 rounded-xl bg-orange-400/5 h-full">
                <Logo class="text-orange-500" />
                <UnitPrice class="!text-center text-orange-500" :show-title="false" price="۲۵.۰۰۰.۰۰۰.۰۰۰"
                    span-class="inline-block" />
            </div>
            <!-- icon -->
            <div
                class="border border-gray-200 w-fit h-fit p-4 rounded-xl absolute inset-x-0 m-auto top-2/4 -translate-y-2/4 bg-white">
                <HugeiconsIcon :icon="CircleArrowReload01Icon" />
            </div>
            <!-- Divar -->
            <div
                class="flex flex-col justify-between gap-y-8 md:gap-y-16 p-6 rounded-xl bg-white border border-gray-200 h-full">
                <div class="flex flex-col">
                    <img :src="Divar" alt="divar icon" class="w-11 h-fit">
                    <p class="text-gray-400 font-light text-sm">قیمت درج شده آگهی در سایت دیوار</p>
                </div>
                <UnitPrice class="!text-center text-black" :show-title="false" price="۳۵.۰۰۰.۰۰۰.۰۰۰"
                    span-class="inline-block" />
            </div>
        </div>
    </div>
</template>


<script setup>
import { Pdf01Icon, Share08Icon, CircleArrowReload01Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

import Divar from '../assets/files/images/Divar2.svg'

import CardTitle from './CardTitle.vue'
import Logo from './Logo.vue'
import Badge from './ui/Badge.vue'
import LinkButton from './ui/LinkButton.vue'
import UnitPrice from './UnitPrice.vue'
</script>