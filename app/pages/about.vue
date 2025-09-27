<template>
    <section
        class="flex flex-col justify-start items-stretch gap-y-4 md:gap-y-20 py-4 md:py-6 overflow-hidden relative">
        <!-- summary -->
        <div class="w-full grid grid-cols-1 items-start lg:grid-cols-2 gap-6">
            <div class="h-full">
                <ul class="flex flex-col items-center justify-between h-full md:items-start gap-6">
                    <li>
                        <Badge title="درباره ما" />
                    </li>
                    <li>
                        <Okazion class=" mb-4 md:my-4" />
                    </li>
                    <li>
                        <p class="md:text-lg text-justify leading-relaxed">سرویس اکازیون بر پایه هوش مصنوعی براساس
                            پارامترهای تخصصی ملک
                            را
                            کارشناسی کرده و براساس تحلیل
                            های جامع برآورد قیمت ملک شما را مشخص می کند.</p>
                    </li>
                    <li class="w-full">
                        <ul class="flex flex-wrap lg:flex-nowrap items-center gap-4">
                            <li class="flex-shrink w-full md:w-full md:flex-shrink">
                                <InfoItem title="تعداد تحلیل ها" subtitle="+65" :icon="AiMagicIcon" />
                            </li>
                            <li class="flex-shrink w-full md:w-full md:flex-shrink">
                                <InfoItem title="مدت فعالیت" subtitle="بیش از 10 سال" :icon="TimeSetting03Icon" />
                            </li>
                            <li class="flex-shrink w-full md:w-full md:flex-shrink">
                                <InfoItem title="تعداد کارشناسان" subtitle="13" :icon="ManWomanIcon" />
                            </li>
                        </ul>
                    </li>
                </ul>
            </div>
            <!-- posters -->
            <div class="w-full grid grid-cols-1 md:grid-cols-12 gap-6 h-full">
                <div class="col-span-3 hidden md:block h-full">
                    <img :src="poster2" alt="" class="w-full h-full object-cover rounded-xl md:h-[350px]">
                </div>
                <div class="col-span-9">
                    <img :src="poster1" alt="" class="w-full h-full object-cover rounded-xl md:h-[350px]">
                </div>
            </div>
        </div>
        <!-- about -->
        <div class="w-full grid grid-cols-1 items-start lg:grid-cols-2 gap-6">
            <div>
                <MainTitle title="درباره ما" en="About us" />
                <p class="md:text-lg text-justify">
                    ما بیش از یک کسب‌وکار، جمعی از مشتاقان به ایجاد تحول هستیم. داستان ما با یک ایده ساده آغاز شد: ارائه
                    راه‌حل‌هایی هوشمندانه و خلاقانه که زندگی را ساده‌تر و کسب‌وکارها را پربازده‌تر کند. تیم ما متشکل از
                    متخصصان باتجربه و پرانگیزه‌ای است که عشق به کار و تعهد به کیفیت را سرلوحه خود قرار داده‌اند. مأموریت
                    ما تنها ارائه محصول یا خدمت نیست، بلکه برقراری ارتباطی پایدار و سازنده با شماست. ما به صداقت، نوآوری
                    و رضایت مشتری باور داریم و این ارزش‌ها در قلب هر آنچه انجام می‌دهیم، می‌تپد. هر پروژه، چه بزرگ و چه
                    کوچک، با دقت و اشتیاقی مثال‌زدنی انجام می‌شود.
                </p>
            </div>
            <div>
                <ul class="flex flex-col gap-6">
                    <li>
                        <MainTitle title="ماموریت ما" en="Our Mission" />
                        <p class="md:text-lg text-justify">
                            ماموریت ما، توانمندسازی افراد و کسب‌وکارها از طریق ارائه راه‌حل‌های نوآورانه و کاربرپسند
                            است. ما متعهد به ارائه بالاترین استانداردهای کیفیت و خدمات هستیم تا بتوانیم ارزشی ماندگار
                            برای مشتریان خود خلق کنیم.
                        </p>
                    </li>
                    <li>
                        <ul class="w-full grid grid-cols-1 md:grid-cols-2 gap-4">
                            <li>
                                <InfoItem title="نوآوری" subtitle="راه‌حل‌های تازه" :show-icon="false" :show-num="true"
                                    number="1" />
                            </li>
                            <li>
                                <InfoItem title="کیفیت" subtitle="استاندارد بالا" :show-icon="false" :show-num="true"
                                    number="2" />
                            </li>
                            <li>
                                <InfoItem title="اعتماد" subtitle="شفاف و پایدار" :show-icon="false" :show-num="true"
                                    number="3" />
                            </li>
                            <li>
                                <InfoItem title="رشد" subtitle="یادگیری مداوم" :show-icon="false" :show-num="true"
                                    number="4" />
                            </li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
        <!-- team -->
        <div class="w-full flex flex-col gap-2 items-center text-center">
            <MainTitle title="تیم ما" en="Our Team" />
            <ul class="w-full flex items-center md:justify-center gap-4 md:gap-6 overflow-x-auto flex-nowrap  py-2 -mx-4 px-4 md:px-0"
                style="scrollbar-width: none; -ms-overflow-style: none;">
                <li class="flex-shrink w-full">
                    <TeamItem :img-src="ali" name="علی سامنی" job="خلافکار اصلی" />
                </li>
                <li class="flex-shrink w-full">
                    <TeamItem :img-src="sina" name="سینا زینی" job="خلافکار" />
                </li>
                <li class="flex-shrink w-full">
                    <TeamItem :img-src="holyali" name="امام علی" job="خلافکار کوفه" />
                </li>
                <li class="flex-shrink w-full">
                    <TeamItem :img-src="ali" name="مک کوئیین" job="خلافکار اصلی" />
                </li>
                <li class="flex-shrink w-full">
                    <TeamItem :img-src="ali" name="کریس رونالدو" job="خلافکار اصلی" />
                </li>
            </ul>
        </div>
        <!-- faq -->
        <div class="w-full flex flex-col gap-2 items-center text-center">
            <MainTitle title="سوالات متداول" en="FAQ" />
            <ul class="flex flex-col gap-4 w-full lg:w-[800px]">
                <li>
                    <BaseAccordion question="هدف از ساخت این سرویس چیست؟" answer="به تو چه" />
                </li>
                <li>
                    <BaseAccordion question="منظور از اُکازیون یعنی چی؟" answer="ندونی بهتره" />
                </li>
                <li>
                    <BaseAccordion question="برای ثبت ملک چیکار کنم؟" answer="یه کاری کن پشمامون بریزه" />
                </li>
                <li>
                    <BaseAccordion question="چی شد که بروسلی رو کشتن؟" answer="بیخیال!" />
                </li>
            </ul>
        </div>
    </section>
</template>

<script setup>
import { TimeSetting03Icon, ManWomanIcon, AiMagicIcon } from '@hugeicons/core-free-icons'

import poster1 from '../../assets/files/images/poster1.png'
import poster2 from '../../assets/files/images/poster2.png'
import InfoItem from '../../components/InfoItem'
import MainTitle from '../../components/MainTitle'
import Okazion from '../../components/Okazion'
import TeamItem from '../../components/TeamItem'
import Badge from '../../components/ui/Badge'
import BaseAccordion from '../../components/ui/BaseAccordion'
import ali from '../assets/files/team/ali.jpg'
import holyali from '../assets/files/team/holyali.jpg'
import sina from '../assets/files/team/sina.jpg'

</script>