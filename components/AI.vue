<template>
    <div class="w-full">
        <!-- title -->
        <div class="flex items-center justify-between lg:justify-start gap-2 bg-orange-500/5 p-6 rounded-xl mb-4">
            <CardTitle title="گزارش کارشناسی ملک" class="!font-semibold" />
            <Badge title="توسط AI" />
        </div>
        <!-- content -->
        <div class="flex flex-col gap-y-4 leading-relaxed text-justify">
            <p>در ادامه، تحلیل و نکات برجسته‌ی آگهی اجاره‌ی آپارتمان ۱۳۷ متری واقع در شاهین شمالی (پونک) را بررسی
                میکنیم.
                شما میتوانید با خرید کامل گزارش تحلیلی به تمامی بخش های گزارش دسترسیامل گزارش تحلیلی به تمامی بخش های گزارش دسترسی داشته باشید.</p>
            <ul class="flex flex-col gap-y-2">
                <li>
                    <div class="flex flex-col gap-y-4">
                        <AITitle title="شاخص های فنی ملک" en="Special Options" :icon="PlazaIcon" />
                        <ol class="flex flex-col gap-y-2 list-disc px-4">
                            <li>
                                <h3 class="font-semibold text-sm">کاربری و متراژ مفید: </h3>
                                <p> ۱۳۷ متر – مناسب خانواده‌های ۳ تا ۵ نفر.</p>
                            </li>
                            <li>
                                <h3 class="font-semibold text-sm">تیپ پلان: </h3>
                                <p> سه‌خوابه با دو مستر - کمیاب‌تر از پلان‌های عادی (ارزش افزوده در بازار).</p>
                            </li>
                            <li>
                                <h3 class="font-semibold text-sm"> نورگیری: </h3>
                                <p> ویو ابدی + دو مستر - شاخص روشنایی بالا.</p>
                            </li>
                        </ol>
                    </div>
                </li>
                <li>
                    <div class="flex flex-col gap-y-4">
                        <AITitle title="شاخص‌های ساختمانی و امکانات" en="Features" :icon="EntranceStairsIcon" />
                        <ol class="flex flex-col gap-y-2 list-disc px-4">
                            <li>
                                <h3 class="font-semibold text-sm">کاربری و متراژ مفید: </h3>
                                <p> ۱۳۷ متر – مناسب خانواده‌های ۳ تا ۵ نفر.</p>
                            </li>
                            <li>
                                <h3 class="font-semibold text-sm">تیپ پلان: </h3>
                                <p> سه‌خوابه با دو مستر - کمیاب‌تر از پلان‌های عادی (ارزش افزوده در بازار).</p>
                            </li>
                            <li>
                                <h3 class="font-semibold text-sm"> نورگیری: </h3>
                                <p> ویو ابدی + دو مستر - شاخص روشنایی بالا.</p>
                            </li>
                        </ol>
                    </div>
                </li>
                <li>
                    <div class="flex flex-col gap-y-4">
                        <AITitle title="خلاصه کارشناسی AI" en="AI Summary" :icon="AiMagicIcon" />
                        <p class="p-6 rounded-xl leading-relaxed bg-black/5 text-black">
                            این واحد با توجه به پلان کمیاب (دو مستر + تک‌واحدی)، موقعیت ممتاز (پونک-شاهین شمالی) و
                            انعطاف مالی، یک گزینه High Demand محسوب می‌شود. تنها نقطه ضعف در آگهی: سال ساخت و جزئیات
                            سیستم تأسیسات ذکر نشده که باید قبل از معامله استعلام شود.
                        </p>
                    </div>
                </li>
            </ul>
            <p>و با نمایش یک جدول امتیازدهی تخصصی ادامه می دهیم:</p>
            <BaseTable />
        </div>
    </div>
</template>

<script setup>
import { PlazaIcon, EntranceStairsIcon, AiMagicIcon } from '@hugeicons/core-free-icons'

import AITitle from '../../components/AITitle.vue'
import CardTitle from '../../components/CardTitle.vue'
import Badge from '../../components/ui/Badge.vue'
import BaseTable from '../../components/ui/BaseTable.vue'
</script>