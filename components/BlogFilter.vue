<template>
    <div class="fixed inset-0 flex justify-end bg-black/50 z-20">
        <div class=" bg-white p-4 w-full h-full md:w-96 border-r border-r-gray-300 ">
            <div class="flex flex-col justify-between h-full">
                <div>
                    <ModalTitle :show-logo="false" :show-title="true" title="فیلتر بلاگ" />
                    <ul class="flex flex-col gap-4 bg-gray-50 mt-4 p-6 rounded-xl "
                        style="scrollbar-width: none; -ms-overflow-style: none;">
                        <li>
                            <div class="flex flex-col gap-4">
                                <div class="flex flex-col gap-2">
                                    <h4 class="text-sm font-semibold">جستجو </h4>
                                    <div class="flex items-center gap-2 h-14">
                                        <BaseInput :show-label="false" :icon="Search01Icon" class="w-full mt-3"
                                            placeholder="مثلا املاک در “پونک”" :show-button="true" />
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
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { Search01Icon } from '@hugeicons/core-free-icons'

import ModalTitle from './ModalTitle'
import BaseInput from './ui/BaseInput'
import BaseSelect from './ui/BaseSelect'
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
