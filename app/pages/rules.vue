<template>
    <section class="flex flex-col justify-center items-center gap-y-4 md:gap-y-8 py-4 md:py-6 relative">
        <div class="md:w-[1024px] flex flex-col gap-y-10">
            <!-- content -->
            <div>
                <MainTitle title="
                قوانین و مقررات" en="Terms & Rules" class="text-center" />
                <div class="flex flex-col gap-y-4 text-justify leading-loose">
                    <p>تهران، به عنوان پایتخت سیاسی و اقتصادی ایران، همواره
                        مقصد اصلی برای
                        جویندگان کار، تحصیل و
                        فرصت‌های زندگی بهتر بوده است. این تمرکز شدید جمعیت و فعالیت، تقاضای سکونت در این کلان‌شهر را
                        به میزان قابل توجهی افزایش داده و در نتیجه، مسئله� اجاره‌بها� به یکی از حادترین دغدغه‌های
                        ساکنان و مهاجران تبدیل شده است. بررسی ابعاد مختلف این مسئله، از عوامل شکل‌گیری تا تأثیرات
                        اجتماعی آن، ضروری به نظر می‌رسد.</p>
                    <ul class="w-full flex flex-col gap-y-6 list-disc pr-4 font-semibold">
                        <li>
                            <h5>ریشه‌های بحران مسکن و اجاره‌بها در تهران را می‌توان در چند عامل کلیدی جستجو کرد:</h5>
                        </li>
                        <li>
                            <h5>ریشه‌های بحران مسکن و اجاره‌بها در تهران را می‌توان در چند عامل کلیدی جستجو کرد:</h5>
                        </li>
                        <li>
                            <h5>ریشه‌های بحران مسکن و اجاره‌بها در تهران را می‌توان در چند عامل کلیدی جستجو کرد:</h5>
                        </li>
                        <li>
                            <h5>ریشه‌های بحران مسکن و اجاره‌بها در تهران را می‌توان در چند عامل کلیدی جستجو کرد:</h5>
                        </li>
                        <li>
                            <h5>تمرکزگرایی بی‌امان: بیشترین حجم مشاغل، وزارتخانه‌ها، دانشگاه‌های برتر و مراکز درمانی
                                کشور در تهران متمرکز شده‌اند. این امر مهاجرت سالانه هزاران نفر از سایر شهرها را به دنبال
                                دارد که همگی متقاضی مسکن هستند و با افزایش تقاضا، قیمت‌ها به طور طبیعی بالا می‌روند.
                            </h5>
                        </li>
                    </ul>
                </div>
            </div>
            <!-- FAQ -->
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
        </div>
    </section>
</template>

<script setup>

import MainTitle from '../../components/MainTitle.vue'
import BaseAccordion from '../../components/ui/BaseAccordion.vue'
</script>