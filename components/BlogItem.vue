<template>
    <div class="flex justify-between flex-wrap md:flex-nowrap items-center rounded-l gap-x-6 gap-y-4">
        <ul :class="listClass + [' flex flex-col gap-y-4 w-full']">
            <li>
                <Badge title="خبر" />
            </li>
            <li>
                <h3 :class="titleClass + [' md:text-lg font-black leading-relaxed']">{{ title }}
                </h3>
                <p v-if="showSummary" class="md:text-lg text-justify text-gray-400 my-2 md:w-11/12 leading-relaxed">{{
                    summary }}</p>
            </li>
            <li>
                <!-- authur & Date -->
                <div class="flex items-center gap-x-6 justify-between">
                    <Authur />
                    <Date />
                </div>
            </li>
        </ul>
        <div v-if="showImg"
            :class="imgClass + [' w-full h-40 md:h-48 flex-shrink-0 rounded-xl overflow-hidden bg-gray-100 flex items-center justify-center']">
            <img :src="imgSrc" alt="" class="w-full h-full object-cover">
        </div>
    </div>
</template>

<script setup>
import Authur from './Authur'
import Date from './Date'
import Badge from './ui/Badge'


defineProps({
    imgSrc: { type: String, required: true },
    showImg: { type: Boolean, default: false },
    showSummary: { type: Boolean, default: false },
    title: { type: String, default: 'عنوان آگهی' },
    summary: { type: String, default: 'خلاصه آگهی' },
    imgClass: {
        type: String,
        default: 'md:w-64'
    },
    listClass: {
        type: String,
        default: 'items-stretch'
    },
    titleClass: {
        type: String,
        default: 'md:w-10/12'
    }
})

</script>1