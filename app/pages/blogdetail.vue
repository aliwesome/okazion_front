<template>
    <section class="flex flex-col justify-start items-center gap-y-4 md:gap-y-8 py-4 md:py-6">
        <div class="w-full md:w-[1024px]">
            <BlogItem title="اجاره‌بها در تهران: چالش بزرگ سکونت در پایتخت" :show-img="true" :img-src="img1"
                class="flex-col" img-class="w-full !h-full" list-class="items-center"
                title-class="w-full text-center" />
            <!-- content -->
            <div class="my-4 flex flex-col gap-y-3 md:text-lg">
                <h2 class="font-bold">تنها در منطقه 22 شاهد رشد تخیلی هستیم!</h2>
                <p class="text-justify leading-relaxed">تهران، به عنوان پایتخت سیاسی و اقتصادی ایران، همواره مقصد اصلی
                    برای جویندگان کار، تحصیل و فرصت‌های
                    زندگی بهتر بوده است. این تمرکز شدید جمعیت و فعالیت، تقاضای سکونت در این کلان‌شهر را به میزان قابل
                    توجهی افزایش داده و در نتیجه، مسئله� اجاره‌بها� به یکی از حادترین دغدغه‌های ساکنان و مهاجران تبدیل شده
                    است. بررسی ابعاد مختلف این مسئله، از عوامل شکل‌گیری تا تأثیرات اجتماعی آن، ضروری به نظر می‌رسد.</p>
                <h2 class="font-bold">تنها در منطقه 22 شاهد رشد تخیلی هستیم!</h2>
                <p class="text-justify leading-relaxed">ریشه‌های بحران مسکن و اجاره‌بها در تهران را می‌توان در چند عامل
                    کلیدی جستجو کرد:
                </p>
                <ul class="list-disc pr-4 text-base">
                    <li>
                        <h3 class="font-bold my-2">تورم و نوسانات قیمت:</h3>
                        <p class="text-justify leading-relaxed">قتصاد ایران در سال‌های اخیر با تورم بالا دست و پنجه نرم
                            کرده است. مسکن به عنوان یک دارایی
                            امن، پناهگاهی برای حفظ ارزش پول سرمایه‌گذاران بوده است. بسیاری از افراد به جای سرمایه‌گذاری
                            در بخش‌های تولیدی، پول خود را به خرید خانه و زمین تزریق می‌کنند. این امر باعث افزایش قیمت
                            ملک و به تبع آن، اجاره‌بها می‌شود.</p>
                    </li>
                    <li>
                        <h3 class="font-bold my-2">تمرکزگرایی بی امان:</h3>
                        <p class="text-justify leading-relaxed">قتصاد ایران در سال‌های اخیر با تورم بالا دست و پنجه نرم
                            کرده است. مسکن به عنوان یک دارایی
                            امن، پناهگاهی برای حفظ ارزش پول سرمایه‌گذاران بوده است. بسیاری از افراد به جای سرمایه‌گذاری
                            در بخش‌های تولیدی، پول خود را به خرید خانه و زمین تزریق می‌کنند. این امر باعث افزایش قیمت
                            ملک و به تبع آن، اجاره‌بها می‌شود.</p>
                    </li>
                </ul>
                <img :src="img3" class="md:w-3/4 rounded-xl mx-auto" alt="">
                <p class="text-justify leading-relaxed">تهران، به عنوان پایتخت سیاسی و اقتصادی ایران، همواره مقصد اصلی
                    برای جویندگان کار، تحصیل و فرصت‌های
                    زندگی بهتر بوده است. این تمرکز شدید جمعیت و فعالیت، تقاضای سکونت در این کلان‌شهر را به میزان قابل
                    توجهی افزایش داده و در نتیجه، مسئله� اجاره‌بها� به یکی از حادترین دغدغه‌های ساکنان و مهاجران تبدیل شده
                    است. بررسی ابعاد مختلف این مسئله، از عوامل شکل‌گیری تا تأثیرات اجتماعی آن، ضروری به نظر می‌رسد.</p>
            </div>
            <!-- info -->
            <BlogInfo />
            <!-- similar blogs -->
            <!-- content -->
            <div class="w-full grid grid-cols-1 items-start gap-4 md:gap-6">
                <div class="col-span-12">
                    <!-- sort and Filter -->
                    <div class="w-full relative z-20 my-6">
                        <!-- title -->
                        <SectionTitle title="مقالات مرتبط" />
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
                            <a href="#" class="pb-6 hover:opacity-50 transition-all block">
                                <BlogItem :show-img="true" :img-src="img3" :show-summary="true"
                                    title="قیمت گذاری منصفانه؟ فقط در اُکازیون"
                                    summary="در سال ۱۴۰۴ بالغ بر ۲۰۰ هزار واحد مسکونی در شهر تهران خالی مانده است و هیچگونه اقدامی" />
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import img1 from '../../assets/files/blog/img1.jpg'
import img2 from '../../assets/files/blog/img2.jpg'
import img3 from '../../assets/files/blog/img3.jpg'
import BlogInfo from '../../components/BlogInfo.vue'
import BlogItem from '../../components/BlogItem.vue'
import SectionTitle from '../../components/SectionTitle.vue'
</script>