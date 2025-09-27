<template>
    <div class="flex items-center flex-wrap justify-between gap-4 py-4 border-t border-b border-gray-200 mt-8">
        <View number="845" class="w-full md:w-auto justify-center" />
        <ul class="flex flex-wrap items-center gap-3 w-full md:w-auto">
            <li class="w-full flex-shrink md:w-auto md:flex-shrink-0">
                <!-- copy link -->
                <div
                    class="w-full flex flex-wrap md:flex-nowrap items-center justify-center  gap-x-4 border border-gray-200 p-3 rounded-xl overflow-hidden">
                    <h6 class="text-gray-300 mb-4 md:mb-0 break-all whitespace-break-spaces md:break-normal md:whitespace-normal">
                        https://okazion.ir/2135asd35asd35asdasd.html
                    </h6>
                    <LinkButton class="w-full justify-center md:p-0 md:border-0" :show-title="false" variant="outline"
                        :icon="Copy02Icon" />
                </div>
            </li>
            <li class="w-full flex-shrink md:w-auto md:flex-shrink-0">
                <LinkButton class="w-full justify-center" :show-title="false" variant="outline" :icon="WhatsappIcon" />
            </li>
            <li class="w-full flex-shrink md:w-auto md:flex-shrink-0">
                <LinkButton class="w-full justify-center" :show-title="false" variant="outline" :icon="TelegramIcon" />
            </li>
        </ul>
    </div>
</template>

<script setup>

import { WhatsappIcon, TelegramIcon, Copy02Icon } from '@hugeicons/core-free-icons'

import LinkButton from './ui/LinkButton'
import View from './view.vue'
</script>