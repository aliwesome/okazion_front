<template>
    <div class="overflow-x-auto rounded-xl scrollbar-hide">
        <table class="min-w-full text-right text-sm overflow-x-auto rounded-xl scrollbar-hide">
            <thead>
                <tr class="bg-gray-50 text-black">
                    <th class="font-medium border border-gray-200 px-4 py-2 whitespace-nowrap">شاخص</th>
                    <th class="font-medium border border-gray-200 px-4 py-2 whitespace-nowrap">توضیح</th>
                    <th class="font-medium border border-gray-200 px-4 py-2 whitespace-nowrap">امتیاز (۱ تا۵)</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">متراژ و تیپ پلان</td>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">۱۳۷ متر / سه‌خوابه / دو خواب مستر
                        (کمیاب)</td>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">
                        <BaseRate />
                    </td>
                </tr>
                <tr>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">نورگیری و ویو</td>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">ویو ابدی + نور طبیعی مناسب</td>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">
                        <BaseRate rate="4" />
                    </td>
                </tr>
                <tr>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">تعداد واحد در طبقه</td>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">تک‌واحدی → حریم خصوصی و امنیت بالا
                    </td>
                    <td class="border border-gray-200 px-4 py-2 whitespace-nowrap">
                        <BaseRate rate="2" />
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>

import BaseRate from './BaseRate'

</script>

<style scoped>
/* Hide scrollbar for Chrome, Safari and Opera */
.scrollbar-hide::-webkit-scrollbar {
    display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.scrollbar-hide {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}
</style>