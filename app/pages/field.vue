<template>
    <section class="flex flex-col justify-start items-start gap-y-4 md:gap-y-8 py-4 md:py-6">
        <!-- top -->
        <div class="grid grid-cols-1 items-center w-full md:grid-cols-2">
            <div>
                <ul class="flex flex-col gap-y-4 md:gap-y-6">
                    <li>
                        <div class="flex flex-col items-center md:items-start gap-y-4">
                            <!-- icon -->
                            <div
                                class="p-2 w-14 h-14 rounded-lg flex justify-center items-center bg-orange-500/15 text-orange-500">
                                <HugeiconsIcon :icon="PlazaIcon" />
                            </div>
                            <!-- content -->
                            <div class="text-center md:text-right">
                                <h2 class="text-2xl font-black mb-2">درخواست گزارش میدانی</h2>
                                <p class="leading-relaxed">شما میتوانید با درخواست کارشناسی میدانی در سرویس اُکازیون از
                                    تمامی مزایای داشتن کارشناس
                                    حرفه ای تا برآورد قیمت دقیق ملک بهره مند شوید.
                                    از فرم ذیل برای ثبت درخواست اقدام کنید.
                                </p>
                            </div>
                        </div>
                    </li>
                    <li>
                        <div class="flex items-center gap-4 flex-wrap md:flex-nowrap">
                            <FieldItem title="کارشناسی مجرب" subtitle="+۲۴" :icon="ManWomanIcon" />
                            <FieldItem title="گزارش حرفه ای" subtitle="توسط کارشناسان"
                                :icon="AiContentGenerator01Icon" />
                            <FieldItem title="قیمت گذاری" subtitle="دقیق" :icon="PercentIcon" />
                        </div>
                    </li>
                    <li>
                        <div class="p-4 bg-orange-500/10 rounded-lg flex items-center justify-between">
                            <Badge title="هزینه کارشناسی" />
                            <Price price="۹۹۹.۰۰۰" :span-class="inline - block" class="!text-2xl" />
                        </div>
                    </li>
                </ul>
            </div>
            <div class="hidden md:block"><img :src="fieldimg" alt="" class="mx-auto"></div>
        </div>
        <!-- features -->
        <ul class="flex items-center w-full gap-4 flex-wrap md:gap-6 md:flex-nowrap">
            <li class="w-full md:flex-shrink">
                <InfoItem title="مرحله اول" subtitle="ثبت درخواست ارزیابی" number="۱" :show-num="true"
                    :show-icon="false" />
            </li>
            <li class="w-full md:flex-shrink">
                <InfoItem title="مرحله دوم" subtitle="تماس با کارفرما" number="۲" :show-num="true" :show-icon="false" />
            </li>
            <li class="w-full md:flex-shrink">
                <InfoItem title="مرحله سوم" subtitle="بررسی تخصصی ملک" number="۳" :show-num="true" :show-icon="false" />
            </li>
            <li class="w-full md:flex-shrink">
                <InfoItem title="مرحله چهارم" subtitle="ارائه گزارش میدانی" number="۴" :show-num="true"
                    :show-icon="false" />
            </li>
        </ul>
        <!-- info & form -->
        <div class="w-full flex flex-col items-center justify-center border-t border-gray-200">
            <div
                class="grid grid-cols-1 items-start justify-center md:grid-cols-2 w-full gap-4 md:gap-6 py-6 md:w-[1024px]">
                <!-- info -->
                <ul class="flex flex-col gap-y-4">
                    <li>
                        <BaseAlert variant="neutral" title="پس از پرداخت کارشناسان اُکازیون با شما تماس میگیرند."
                            class="w-fit text-right md:text-center" />
                    </li>
                    <li>
                        <BaseAlert variant="neutral" title="آدرس ملک خود را دقیق بنویسید."
                            class="w-fit text-right md:text-center" />
                    </li>
                    <li>
                        <BaseAlert variant="neutral"
                            title="اطلاعات فرم را به دقت پر کنید تا مشکلی برای ارتباط  با شما وجود نداشته باشد."
                            class="w-fit text-right md:text-center" />
                    </li>
                </ul>
                <!-- form -->
                <div class="p-6 border border-gray-200 rounded-xl">
                    <AITitle class="pt-0 mb-4" title="فرم درخواست" en="request form" :icon="DocumentAttachmentIcon" />
                    <form action="">
                        <ul class="flex flex-col gap-y-4">
                            <li>
                                <BaseInput label="شماره موبایل" placeholder="۰۹xxxxxxxxx" :show-icon="true"
                                    :icon="SmartPhone01Icon" maxlength="11" variant="error" :show-error="true" />
                            </li>
                            <li>
                                <BaseTextarea label="آدرس ملک شما" placeholder="بصورت دقیق بنویسید"
                                    :icon="Location06Icon" :show-icon="true" />
                            </li>
                            <li>
                                <div class="flex items-center justify-between gap-x-4">
                                    <Price price="۹۹۹.۰۰۰" :span-class="inline - block" />
                                    <LinkButton title="ثبت و پرداخت" :icon="WavingHand02Icon"
                                        class="!text-black px-5 w-full md:w-fit justify-center" variant="success" />
                                </div>
                            </li>
                        </ul>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { PlazaIcon, ManWomanIcon, AiContentGenerator01Icon, PercentIcon, DocumentAttachmentIcon, SmartPhone01Icon, Location06Icon, WavingHand02Icon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

import fieldimg from '../../assets/files/images/field.png'
import AITitle from '../../components/AITitle.vue'
import FieldItem from '../../components/FieldItem.vue'
import InfoItem from '../../components/InfoItem.vue'
import Price from '../../components/Price.vue'
import Badge from '../../components/ui/Badge.vue'
import BaseAlert from '../../components/ui/BaseAlert.vue'
import BaseInput from '../../components/ui/BaseInput.vue'
import BaseTextarea from '../../components/ui/BaseTextarea.vue'
import LinkButton from '../../components/ui/LinkButton.vue'
</script>