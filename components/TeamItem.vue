<template>
    <div class="w-64 lg:w-full rounded-xl relative overflow-hidden">
        <img :src="imgSrc" alt="" class="w-full object-cover rounded-xl">
        <div
            class="after:content-[''] after:absolute after:inset-0 after:bg-gradient-to-t after:from-black after:to-transparent" />
        <!-- content -->
        <div class="absolute z-20 bottom-0 w-full text-white py-6 px-2">
            <ul class="flex flex-col gap-1">
                <li>
                    <h3 class="font-black text-2xl md:text-3xl">{{ name }}</h3>
                </li>
                <li>
                    <h4 class="font-thin text-xl md:text-2xl">{{ job }}</h4>
                </li>
                <li>
                    <div class="flex justify-center items-center gap-3 mt-2">
                        <LinkButton :icon="Linkedin01Icon" :show-title="false" variant="outline"
                            class="text-white border-none !p-0" />
                        <LinkButton :icon="TelegramIcon" :show-title="false" variant="outline"
                            class="text-white border-none !p-0" />
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script setup>
import { Linkedin01Icon, TelegramIcon } from '@hugeicons/core-free-icons'

import LinkButton from './ui/LinkButton'


defineProps({
    imgSrc: { type: String, required: true },
    name: { type: String, default: 'اسم داداشمون' },
    job: { type: String, default: 'شغل' },
})

</script>