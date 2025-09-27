<template>
    <section class="flex justify-center items-start gap-y-4 md:gap-y-8 py-4 md:py-6">
        <div class="w-full flex flex-col gap-y-4 md:w-[500px]">
            <Back title="فاکتور خرید" />
            <!-- factors -->
            <div class="bg-white px-6 py-8 rounded-xl border border-gray-200 overflow-hidden">
                <!-- factor - #1 -->
                <div class="">
                    <PaymentMessage title="پرداخت شما با موفقیت انجام شد" />
                    <!-- list -->
                    <ul class="flex flex-col gap-y-4">
                        <li>
                            <div class="flex items-center justify-between text-sm">
                                <span class="font-bold">مبلغ</span>
                                <Price price="۴۰.۰۰۰" span-class="inline-block" class="!text-gray-400 font-semibold" />
                            </div>
                        </li>
                        <li>
                            <div class="flex items-center justify-between text-sm">
                                <span class="font-bold">توضیحات</span>
                                <p class="text-gray-400 font-semibold">درخواست گزارش تکمیلی</p>
                            </div>
                        </li>
                        <li>
                            <div class="flex items-center justify-between text-sm">
                                <span class="font-bold">شماره پیگیری</span>
                                <p class="text-gray-400 font-semibold">OK-۷۱۲۳۴۵</p>
                            </div>
                        </li>
                    </ul>
                    <!-- actions -->
                    <div class="mt-6 flex flex-col gap-4">
                        <!-- buttons -->
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <LinkButton title="مشاهده گزارش" variant="black" direction="right" :icon="AiMagicIcon"
                                class="w-full justify-center" />
                            <LinkButton title="دانلود PDF گزارش" variant="outline" direction="right" :icon="Pdf01Icon"
                                class="w-full justify-center" />
                        </div>
                        <!-- alert -->
                        <BaseAlert title="لینک گزارش به شماره ۰۹۱۲۰۴۱۴۶۵۹ ارسال شد" />
                    </div>
                    <!-- logo -->
                    <div class="relative -bottom-5 mt-12">
                        <Okazion fa-class="text-gray-200" />
                    </div>
                </div>
                <!-- factor - #2 -->
                <div class="hidden">
                    <PaymentMessage title="مشکل در انجام تراکنش بوجود آمد" :icon="SadDizzyIcon" class="text-rose-500"
                        icon-class="bg-rose-500/10 text-rose-500" />
                    <!-- list -->
                    <ul class="flex flex-col gap-y-4">
                        <li>
                            <div class="flex items-center justify-between text-sm">
                                <span class="font-bold">مبلغ</span>
                                <Price price="۴۰.۰۰۰" span-class="inline-block" class="!text-gray-400 font-semibold" />
                            </div>
                        </li>
                        <li>
                            <div class="flex items-center justify-between text-sm">
                                <span class="font-bold">توضیحات</span>
                                <p class="text-gray-400 font-semibold">درخواست گزارش تکمیلی</p>
                            </div>
                        </li>
                        <li>
                            <div class="flex items-center justify-between text-sm">
                                <span class="font-bold">شماره پیگیری</span>
                                <p class="text-gray-400 font-semibold">OK-۷۱۲۳۴۵</p>
                            </div>
                        </li>
                    </ul>
                    <!-- actions -->
                    <div class="mt-6 flex flex-col gap-4">
                        <!-- info -->
                        <ul class="flex flex-col gap-y-4 border-t border-gray-200 pt-4">
                            <li>
                                <div class="text-sm">
                                    <h3 class="font-bold mb-1">آدرس</h3>
                                    <p class="leading-relaxed text-gray-400 text-justify">تهران، پونک، خیابان سیمون
                                        بولیوار، انتهای خیابان الوند، برج های بام پونک، بلوک بی
                                        یک، طبقه پنج، واحد دو</p>
                                </div>
                            </li>
                            <li>
                                <div class="text-sm">
                                    <h3 class="font-bold mb-1">اطلاعات تماس</h3>
                                    <p class="leading-relaxed text-gray-400">
                                        ۰۹۱۲۰۴۱۴۶۵۹
                                    </p>
                                </div>
                            </li>
                        </ul>
                        <!-- alert -->
                        <BaseAlert title="کارشناسان اُکازیون بزودی با شما تماس میگیرند" />
                    </div>
                    <!-- logo -->
                    <div class="relative -bottom-5 mt-12">
                        <Okazion fa-class="text-gray-200" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { AiMagicIcon, Pdf01Icon, SadDizzyIcon } from '@hugeicons/core-free-icons'

import Back from '../../components/Back.vue'
import Okazion from '../../components/Okazion.vue'
import PaymentMessage from '../../components/PaymentMessage.vue'
import Price from '../../components/Price.vue'
import BaseAlert from '../../components/ui/BaseAlert.vue'
import LinkButton from '../../components/ui/LinkButton.vue'
</script>