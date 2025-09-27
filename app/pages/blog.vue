<template>
    <section class="flex flex-col justify-center items-center gap-y-4 md:gap-y-8 py-4 md:py-6 overflow-hidden relative">
        <!-- Search -->
        <div class="flex flex-col gap-y-2 items-center text-center w-full md:w-[600px]">
            <Badge title="مجله اُکازیون" class="mb-4" />
            <h2 class="text-xl md:text-2xl font-black">بهترین و برترین تحلیل های املاک</h2>
            <p class="font-light text-gray-400">در این بخش مقالات و تحلیل های کارشناسان سرویس اُکازیون رو مشاهده میکنید
            </p>
            <BaseInput :show-label="false" :icon="Search01Icon" class="w-full mt-3" placeholder="مثلا املاک در “پونک”"
                :show-button="true" input-class="p-7" />
        </div>
        <!-- slideshow -->
        <div>
            <BlogGallery />
        </div>

        <!-- content -->
        <div class="w-full grid grid-cols-1 lg:grid-cols-12 items-start gap-4 md:gap-6">
            <div class="col-span-12 lg:col-span-8">
                <!-- sort and Filter -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-y-4 w-full relative z-20 mb-6">
                    <!-- title -->
                    <SectionTitle title="تازه های امروز" />
                    <!-- sort and Filter -->
                    <div class="w-full md:w-auto flex items-center h-14 gap-x-2 place-self-end flex-nowrap">
                        <BaseSelect :options="[
                            { label: 'جدیدترین', value: 'newest' },
                            { label: 'قدیمی‌ترین', value: 'oldest' }
                        ]" placeholder="مرتب‌سازی" class="w-full flex-shrink" />
                        <Button class="flex-shrink w-full h-full justify-center" title="فیلتر"
                            :icon="FilterHorizontalIcon" direction="right" variant="black" />
                    </div>
                </div>
                <ul class="flex flex-col gap-y-4 md:gap-y-6">
                    <li>
                        <a href="#" class="border-b border-gray-200 pb-6 hover:opacity-50 transition-all block">
                            <BlogItem :show-img="true" :img-src="img2" :show-summary="true"
                                title="کارشناسی واحدهای تجاری در شیراز"
                                summary="در سال ۱۴۰۴ بالغ بر ۲۰۰ هزار واحد مسکونی در شهر تهران خالی مانده است و هیچگونه اقدامی" />
                        </a>
                    </li>
                    <li>
                        <a href="#" class="border-b border-gray-200 pb-6 hover:opacity-50 transition-all block">
                            <BlogItem :show-img="true" :img-src="img1" :show-summary="true"
                                title="تهران، ت*می ترین شهر دنیا"
                                summary="در سال ۱۴۰۴ بالغ بر ۲۰۰ هزار واحد مسکونی در شهر تهران خالی مانده است و هیچگونه اقدامی" />
                        </a>
                    </li>
                    <li>
                        <a href="#" class="border-b border-gray-200 pb-6 hover:opacity-50 transition-all block">
                            <BlogItem :show-img="true" :img-src="img3" :show-summary="true"
                                title="قیمت گذاری منصفانه؟ فقط در اُکازیون"
                                summary="در سال ۱۴۰۴ بالغ بر ۲۰۰ هزار واحد مسکونی در شهر تهران خالی مانده است و هیچگونه اقدامی" />
                        </a>
                    </li>
                </ul>
            </div>
            <div class="col-span-12 lg:col-span-4">
                <!-- social media -->
                <div class="w-full p-6 text-center rounded-xl bg-orange-500/5">
                    <h2 class="mb-6">ما را در شبکه‌های اجتماعی دنبال کنید</h2>
                    <SocialMedia class="!justify-center" />
                </div>
            </div>
        </div>
        <Pagination />
        <BlogFilter class="hidden" />
    </section>
</template>

<script setup>
import { Search01Icon, FilterHorizontalIcon } from '@hugeicons/core-free-icons'

import img1 from '../../assets/files/blog/img1.jpg'
import img2 from '../../assets/files/blog/img2.jpg'
import img3 from '../../assets/files/blog/img3.jpg'
import BlogFilter from '../../components/BlogFilter.vue'
import BlogGallery from '../../components/bloggallery'
import BlogItem from '../../components/BlogItem.vue'
import SectionTitle from '../../components/SectionTitle.vue'
import SocialMedia from '../../components/SocialMedia.vue'
import Badge from '../../components/ui/Badge.vue'
import BaseInput from '../../components/ui/BaseInput.vue'
import BaseSelect from '../../components/ui/BaseSelect.vue'
import Button from '../../components/ui/Button.vue'
import Pagination from '../../components/ui/Pagination.vue'
</script>