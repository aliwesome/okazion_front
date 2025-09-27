<template>
    <section class="flex flex-col justify-center items-center gap-y-4 md:gap-y-8 py-4 md:py-6">
        <!-- logo -->
        <div class="relative my-10">
            <Okazion />
        </div>
        <div class="w-full flex flex-col gap-y-4 md:w-[500px]">
            <Back title="ثبت فرم همکاری" />
            <!-- form -->
            <div class="bg-white p-6 rounded-xl border border-gray-200 overflow-hidden">
                <form class="">
                    <!-- list -->
                    <ul class="grid grid-cols-1 md:grid-cols-12 gap-4">
                        <li class="col-span-12">
                            <BaseInput label="نام شرکت / املاک" placeholder="مثلا “مشاور املاک ایران”" :show-icon="true"
                                :icon="City01Icon" />
                        </li>
                        <li class="col-span-12 md:col-span-6">
                            <BaseInput label="نام" placeholder="مثلا “علی”" :show-icon="true" :icon="User02Icon" />
                        </li>
                        <li class="col-span-12 md:col-span-6">
                            <BaseInput label="نام خانوادگی" placeholder="مثلا “سامنی”" :show-icon="true"
                                :icon="User02Icon" />
                        </li>
                        <li class="col-span-12 md:col-span-6">
                            <BaseInput label="شماره موبایل" placeholder="09xxxxxxxx" maxlength="11" :show-icon="true"
                                :icon="SmartPhone01Icon" />
                        </li>
                        <li class="col-span-12 md:col-span-6">
                            <BaseSelect label="مدت فعالیت" :show-label="true" :options="[
                                { label: '8 سال', value: 'newest' },
                                { label: '5 سال', value: 'oldest' }
                            ]" placeholder="انتخاب کنید" />
                        </li>
                        <li class="col-span-12">
                            <BaseTextarea label="پیام خود را بنویسید" placeholder="هر درخواست، نظری دارید بنویسید"
                                :show-icon="true" :icon="Message01Icon" />
                        </li>
                        <li class="col-span-12 place-self-end w-full md:w-fit">
                            <Button title="ثبت و ارسال" direction="right" :icon="TelegramIcon"
                                class="w-full justify-center" />
                        </li>
                    </ul>
                </form>
            </div>
            <!-- alerts -->
            <div class="flex flex-col gap-y-4">
                <BaseAlert class="text-justify"
                    title="صاحبین شرکت ها، مشاورین املاک و کارشناسان می توانند با ارسال اطلاعات  همکاری بررسی نهایی اطلاعات  خود را با مجموعه تحت عنوان کارشناس شروع کنند." />
                <BaseAlert class="text-justify" variant="info"
                    title="توجه داشته باشید که تمامی مجوزهای لازم برای کارشناسی ملک از جمله مدرک گواهینامه الزامی می باشد." />
            </div>
        </div>
    </section>
</template>

<script setup>
import { City01Icon, User02Icon, SmartPhone01Icon, Message01Icon, TelegramIcon } from '@hugeicons/core-free-icons'

import Back from '../../components/Back.vue'
import Okazion from '../../components/Okazion.vue'
import BaseAlert from '../../components/ui/BaseAlert.vue'
import BaseInput from '../../components/ui/BaseInput.vue'
import BaseSelect from '../../components/ui/BaseSelect.vue'
import BaseTextarea from '../../components/ui/BaseTextarea.vue'
import Button from '../../components/ui/Button.vue'
</script>