<template>
    <section class="flex justify-start flex-col items-start gap-y-4 md:gap-y-6 py-4 md:py-6 lg:h-screen">
        <!-- sort and Filter -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-y-4 items-end w-full relative z-20">
            <!-- title -->
            <div class="flex items-center gap-2">
                <SectionTitle title="لیست آگهی ها" />
                <span class="text-gray-400">(۸۵)</span>
            </div>
            <!-- sort and Filter -->
            <div class="w-full md:w-auto flex items-center h-full gap-x-2 place-self-end flex-nowrap">
                <BaseSelect :options="[
                    { label: 'جدیدترین', value: 'newest' },
                    { label: 'قدیمی‌ترین', value: 'oldest' }
                ]" placeholder="مرتب‌سازی" />
                <Button class="flex-shrink w-full justify-center" title="فیلتر" :icon="FilterHorizontalIcon"
                    direction="right" variant="black" />
            </div>
        </div>
        <!-- content -->
        <ul class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 md:gap-6">
            <li>
                <AdvCard class="!w-full" :img-src="adv1" />
            </li>
            <li>
                <AdvCard class="!w-full" :img-src="adv2" />
            </li>
            <li>
                <AdvCard class="!w-full" :img-src="adv3" />
            </li>
            <li>
                <AdvCard class="!w-full" :img-src="adv1" />
            </li>
            <li>
                <AdvCard class="!w-full" :img-src="adv2" />
            </li>
            <li>
                <AdvCard class="!w-full" :img-src="adv3" />
            </li>
        </ul>
        <!-- pagination -->
        <Pagination />
        <!-- Filter -->
        <Filter class="hidden" />
    </section>
</template>

<script setup>
import { FilterHorizontalIcon } from '@hugeicons/core-free-icons'


import AdvCard from '../../components/AdvCard.vue'
import Filter from '../../components/Filter.vue'
import SectionTitle from '../../components/SectionTitle.vue'
import BaseSelect from '../../components/ui/BaseSelect.vue'
import Button from '../../components/ui/Button.vue'
import Pagination from '../../components/ui/Pagination.vue'
import adv1 from '../assets/files/adv/adv1.jpg'
import adv2 from '../assets/files/adv/adv2.jpg'
import adv3 from '../assets/files/adv/adv3.jpg'
</script>