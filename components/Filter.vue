<template>
    <div class="fixed inset-0 flex justify-end bg-black/50 z-20">
        <div class=" bg-white p-4 w-full h-full md:w-96 border-r border-r-gray-300 ">
            <div class="flex flex-col justify-between h-full">
                <div>
                    <ModalTitle :show-logo="false" :show-title="true" title="فیلتر آگهی ها" />
                    <ul class="flex flex-col gap-4 bg-gray-50 mt-4 p-6 overflow-y-auto max-h-[calc(100vh-6rem)] rounded-xl md:max-h-none scrollbar-hide"
                        style="scrollbar-width: none; -ms-overflow-style: none;">
                        <li>
                            <div class="flex flex-col gap-4">
                                <div class="flex flex-col gap-2">
                                    <h4 class="text-sm font-semibold">قیمت <span
                                            class="text-xs text-gray-400">(تومان)</span></h4>
                                    <div class="flex items-center gap-2 h-14">
                                        <span>از</span>
                                        <BaseSelect class="w-full flex-shrink" :options="[
                                            { label: '520.000.000', value: 'one' },
                                            { label: '25.000.000.000', value: 'two' }
                                        ]" placeholder="مثلا 10.000.000" />
                                    </div>
                                </div>
                                <div class="flex flex-col gap-2">
                                    <div class="flex items-center gap-2 h-14">
                                        <span>تا</span>
                                        <BaseSelect class="w-full flex-shrink" :options="[
                                            { label: '520.000.000', value: 'one' },
                                            { label: '25.000.000.000', value: 'two' }
                                        ]" placeholder="مثلا 30.000.000.000" />
                                    </div>
                                </div>
                            </div>
                        </li>
                        <li>
                            <div class="flex flex-col gap-4">
                                <div class="flex flex-col gap-2">
                                    <h4 class="text-sm font-semibold">متراژ <span
                                            class="text-xs text-gray-400">(متر)</span></h4>
                                    <div class="flex items-center gap-2 h-14">
                                        <span>از</span>
                                        <BaseSelect class="w-full flex-shrink" :options="[
                                            { label: '200 متر', value: 'one' },
                                            { label: '400 متر', value: 'two' }
                                        ]" placeholder="مثلا 100 متر" />
                                    </div>
                                </div>
                                <div class="flex flex-col gap-2">
                                    <div class="flex items-center gap-2 h-14">
                                        <span>تا</span>
                                        <BaseSelect class="w-full flex-shrink" :options="[
                                            { label: '800 متر', value: 'one' },
                                            { label: '1000 متر', value: 'two' }
                                        ]" placeholder="مثلا 1000 متر" />
                                    </div>
                                </div>
                            </div>
                        </li>
                        <li>
                            <div class="flex flex-col gap-4">
                                <div class="flex flex-col gap-2">
                                    <h4 class="text-sm font-semibold">منطقه</h4>
                                    <div class="h-14 flex items-center gap-2">
                                        <BaseSelect class="w-full flex-shrink" :options="[
                                            { label: 'تهران', value: 'one' },
                                            { label: 'مازندران', value: 'two' }
                                        ]" placeholder="انتخاب کنید" />
                                    </div>
                                </div>
                            </div>
                        </li>
                        <li>
                            <div class="flex flex-col gap-4">
                                <div class="flex flex-col gap-2">
                                    <h4 class="text-sm font-semibold">اتاق</h4>
                                    <div class="h-14 flex items-center gap-2">
                                        <BaseSelect class="w-full flex-shrink" :options="[
                                            { label: 'بدون اتاق', value: 'one' },
                                            { label: '2 اتاق', value: 'two' }
                                        ]" placeholder="انتخاب کنید" />
                                    </div>
                                </div>
                            </div>
                        </li>
                        <li>
                            <div class="flex flex-col gap-4">
                                <div class="flex items-center justify-between gap-2">
                                    <span class="text-sm">با آسانسور</span>
                                    <BaseSwitch />
                                </div>
                                <div class="flex items-center justify-between gap-2">
                                    <span class="text-sm">با انباری</span>
                                    <BaseSwitch :model-value="true" />
                                </div>
                                <div class="flex items-center justify-between gap-2">
                                    <span class="text-sm">با پارکینگ</span>
                                    <BaseSwitch />
                                </div>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import ModalTitle from './ModalTitle'
import BaseSelect from './ui/BaseSelect'
import BaseSwitch from './ui/BaseSwitch'
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar {
    display: none;
}

.scrollbar-hide {
    -ms-overflow-style: none;
    scrollbar-width: none;
}
</style>
