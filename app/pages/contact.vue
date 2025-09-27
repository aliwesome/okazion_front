<template>
    <section
        class="flex flex-col justify-start items-start gap-y-4 md:gap-y-8 py-4 md:py-6 overflow-hidden relative">
        <div class="w-full grid grid-cols-1 justify-center center md:grid-cols-11 gap-4 md:gap-6">
            <!-- poster -->
            <div class="order-2 md:order-1 md:col-span-3">
                <div class="relative rounded-lg">
                    <img :src="img1" alt="" class="object-cover w-full rounded-lg">
                    <!-- content -->
                    <div class="absolute p-6 inset-0 flex flex-col justify-between items-center justify-center">
                        <okazion fa-class="text-white" class="h-full" />
                        <!-- social media -->
                        <div class="flex flex-col justify-start gap-y-3 w-full">
                            <h5 class="text-white font-medium"><span class="block">اُکازیون</span> در شبکه های اجتماعی
                            </h5>
                            <div class="w-fit">
                                <SocialMedia class="text-white justify-center" />
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!-- content -->
            <div class="order-1 md:order-2 md:col-span-8">
                <!-- title -->
                <div class="flex flex-col items-center text-center gap-4 mb-6 md:flex-row md:text-right">
                    <div
                        class="p-2 w-14 h-14 rounded-lg flex justify-center items-center bg-orange-500/15 text-orange-500">
                        <HugeiconsIcon :icon="TelephoneIcon" class="w-7 h-7" />
                    </div>
                    <div>
                        <h3 class="font-black text-lg">تماس با ما</h3>
                        <p class="text-gray-400">با تکمیل فرم ذیل می توانید با ما در ارتباط باشید.</p>
                    </div>
                </div>
                <!-- form -->
                <form>
                    <ul class="w-full grid grid-cols-1 gap-6 md:grid-cols-12">
                        <li class="md:col-span-4">
                            <BaseInput label="نام" placeholder="مثلا “علی”" :show-icon="true" />
                        </li>
                        <li class="md:col-span-4">
                            <BaseInput label="نام خانوادگی" placeholder="مثلا “سامنی”" :show-icon="true" />
                        </li>
                        <li class="md:col-span-4">
                            <BaseInput label="شماره موبایل" placeholder="09xxxxxxxx" :show-icon="true"
                                :icon="SmartPhone01Icon" />
                        </li>
                        <li class="md:col-span-12">
                            <BaseTextarea label="پیام شما" placeholder="هر درخواست، نظری دارید بنویسید"
                                :show-icon="true" :icon="Message01Icon" />
                        </li>
                        <li class="md:col-span-12 place-self-end">
                            <Button title="ثبت و ارسال" direction="right" :icon="TelegramIcon"
                                class="w-full md:w-auto justify-center" />
                        </li>
                    </ul>
                </form>
            </div>
        </div>
    </section>
</template>

<script setup>
import { TelephoneIcon, SmartPhone01Icon, Message01Icon, TelegramIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'

import img1 from '../../assets/files/images/contact.jpg'
import okazion from '../../components/okazion'
import SocialMedia from '../../components/SocialMedia'
import BaseInput from '../../components/ui/BaseInput'
import BaseTextarea from '../../components/ui/BaseTextarea'
import Button from '../../components/ui/Button'
</script>