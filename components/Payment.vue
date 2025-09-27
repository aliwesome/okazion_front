<template>
    <div class="fixed flex justify-center items-end lg:items-center bg-black/50 right-0 left-0 bottom-0 top-0 z-10">
        <div class="bg-white p-4 md:p-8 w-full h-4/5 md:h-fit md:w-[800px] rounded-xl overflow-hidden">
            <div class="flex flex-col gap-y-10">
                <ModalTitle :show-title="true" title="دریافت گزارش تکمیلی ملک" />
                <!-- content -->
                <ul class="w-full flex flex-col gap-y-6 items-center justify-center">
                    <li class="w-full md:w-1/2">
                        <BaseInput label="شماره موبایل" placeholder="۰۹xxxxxxxx" :show-icon="true"
                            :icon="SmartPhone01Icon" maxlength="11" />
                    </li>
                    <li class="w-full md:w-1/2">
                        <div class="flex flex-col gap-y-2 items-center md:flex-row justify-between">
                            <Price price="۴۰.۰۰۰" class="!text-2xl" span-class="inline-block" />
                            <LinkButton title="پرداخت" :icon="WavingHand02Icon"
                                class="!text-black px-5 w-full md:w-fit justify-center" variant="success" />
                        </div>
                    </li>
                    <li class="w-full md:w-1/2">
                        <BaseAlert title="پس از پرداخت، گزارش تکمیلی برای شما ارسال خواهد شد." />
                    </li>
                </ul>
                <div class="relative md:-bottom-5">
                    <Okazion fa-class="text-gray-200" />
                </div>
            </div>
        </div>
    </div>
</template>


<script setup>
import { SmartPhone01Icon, WavingHand02Icon } from '@hugeicons/core-free-icons'

import ModalTitle from './ModalTitle.vue'
import Okazion from './Okazion.vue'
import Price from './Price.vue'
import BaseAlert from './ui/BaseAlert.vue'
import BaseInput from './ui/BaseInput.vue'
import LinkButton from './ui/LinkButton.vue'
</script>