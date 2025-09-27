<template>
    <section class="flex flex-col items-start gap-y-4 md:gap-y-8 py-4 md:py-6">
        <!-- top -->
        <div class="w-full grid grid-cols-1 lg:grid-cols-3 gap-4 md:gap-x-6">
            <!-- adv title & badges -->
            <div class="flex flex-col gap-y-5 order-2 md:order-1">
                <AdvTitle title="۱۰۰ متر دو خواب شهرک راه آهن/ ۲ ساله سروستان/کوهک"
                    address="تهران، مرادآباد، خیابان الوند، برج های بام پونک، بلوک بی ۱، طبقه ۵، واحد ۲ "
                    class="!text-lg" />
                <!-- Ads badges -->
                <ul class="flex  items-stretch  flex-wrap gap-2">
                    <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                        <AdvBadge title="رشد منطقه" subtitle="۶۰% نسبت به ۱۴۰۳" variant="silver" :img-src="silver" />
                    </li>
                    <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                        <AdvBadge title="تحلیل AI" subtitle="اُکازیون" variant="champion" :show-icon="false"
                            :img-src="champion" />
                    </li>
                    <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                        <AdvBadge title="قیمت واحد" subtitle="معقول" variant="gold" :show-icon="false"
                            :img-src="gold" />
                    </li>
                    <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                        <AdvBadge title="موقعیت ملک" subtitle="عالی" variant="platinum" :show-icon="false"
                            :img-src="platinum" />
                    </li>
                    <li class="flex-grow w-5/12 md:flex-grow-0 md:w-fit">
                        <AdvBadge title="ارزش منطقه" subtitle="بالا" variant="diamond" :show-icon="false"
                            :img-src="diamond" />
                    </li>

                </ul>
            </div>
            <!-- gallery -->
            <div class="order-3 md:order-2">
                <Gallery />
            </div>
            <!-- price compare -->
            <div class="order-1 md:order-3">
                <PriceCompare />
            </div>
        </div>
        <!-- info -->
        <div class="flex w-full flex-col gap-4">
            <SectionTitle title="درباره واحد" />
            <div class="w-full overflow-x-auto">
                <ul class="flex items-center gap-4 overflow-x-auto flex-nowrap md:flex-wrap lg:flex-nowrap"
                    style="scrollbar-width: none; -ms-overflow-style: none;">
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="متراژ" subtitle="۸۵ مترمربع" />
                    </li>
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="نوع" subtitle="آپارتمان" :icon="PlazaIcon" />
                    </li>
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="طبقه" subtitle="۲" :icon="FloorPlanIcon" />
                    </li>
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="واحد" subtitle="۳" :icon="Key01Icon" />
                    </li>
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="پارکینگ" subtitle="دارد" :icon="CarParking02Icon" />
                    </li>
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="انباری" subtitle="دارد" :icon="WarehouseIcon" />
                    </li>
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="آسانسور" subtitle="دارد" :icon="ArrowReloadVerticalIcon" />
                    </li>
                    <li class="flex-shrink-0 w-48 md:flex-shrink">
                        <InfoItem title="سال ساخت" subtitle="۱۴۰۴" :icon="CraneIcon" />
                    </li>
                </ul>
            </div>
        </div>
        <!-- access & map -->
        <div class="flex flex-col gap-4 w-full">
            <CardTitle title="موقعیت و دسترسی واحد" :icon="RouteBlockIcon" />
            <div class="grid grid-cols-1 md:grid-cols-2 items-center gap-4">
                <!-- access -->
                <div>
                    <ul class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
                        <li class="border-b border-l border-gray-200">
                            <AccessItem title="بانک" distance="۸۰۰ متر" :icon="BankIcon" />
                        </li>
                        <li class="border-b border-gray-200 md:border-l">
                            <AccessItem title="پمپ بنزین" distance="۳ کیلومتر" :icon="PetrolPumpIcon" />
                        </li>
                        <li class="border-b border-l md:border-l-0 lg:border-l border-gray-200">
                            <AccessItem title="پارک" distance="۱۰۰ متر" :icon="Tree06Icon" />
                        </li>
                        <li class="border-b border-gray-200 md:border-l lg:border-l-0">
                            <AccessItem title="داروخانه" distance="۲ کیلومتر" :icon="MedicineBottle01Icon" />
                        </li>
                        <li class="border-b border-l border-gray-200 lg:border-b-0">
                            <AccessItem title="مترو" distance="۴ کیلومتر" :icon="MetroIcon" />
                        </li>
                        <li class="border-b border-gray-200 lg:border-b-0 lg:border-l">
                            <AccessItem title="بی آر تی" distance="۱.۵ کیلومتر" :icon="Bus01Icon" />
                        </li>
                        <li class=" border-gray-200 border-l lg:border-b-0">
                            <AccessItem title="مدرسه" distance="۲ کیلومتر" :icon="Backpack01Icon" />
                        </li>
                        <li class=" border-gray-200 lg:border-b-0">
                            <AccessItem title="بیمارستان" distance="۱۰ کیلومتر" :icon="Hospital01Icon" />
                        </li>
                    </ul>
                </div>
                <!-- map -->
                <div class="w-full h-64 rounded-xl overflow-hidden border border-gray-200">
                    <iframe width="100%" height="100%" style="border:0" allowfullscreen
                        referrerpolicy="no-referrer-when-downgrade"
                        src="https://www.openstreetmap.org/export/embed.html?bbox=51.3790%2C35.6792%2C51.3990%2C35.6992&amp;layer=mapnik&amp;marker=35.6892,51.3890" />
                </div>

            </div>
        </div>
        <!-- analysis -->
        <div class="w-full flex flex-col gap-y-6 items-center">
            <AI />
            <LinkButton title="مشاهده گزارش کامل" direction="right" variant="black" :icon="AiMagicIcon" />
        </div>
        <!-- ADS Part -->
        <div class="w-full flex justify-center mt-10">
            <div class="flex flex-col gap-4 w-full md:w-[1024px]">
                <SectionTitle title="برترین های اُکازیون" />
                <ul class="flex items-center md:justify-center gap-4 md:gap-6 overflow-x-auto flex-nowrap md:flex-wrap py-2 -mx-4 px-4"
                    style="scrollbar-width: none; -ms-overflow-style: none;">
                    <li class="flex-shrink-0 w-80">
                        <AdvCard :img-src="adv1" />
                    </li>
                    <li class="flex-shrink-0 w-80">
                        <AdvCard :img-src="adv2" />
                    </li>
                    <li class="flex-shrink-0 w-80">
                        <AdvCard :img-src="adv3" />
                    </li>
                </ul>
            </div>
        </div>

        <!-- Payment Modal -->
        <Payment class="hidden" />
    </section>
</template>

<script setup>
import { AiMagicIcon, RouteBlockIcon, PlazaIcon, FloorPlanIcon, Key01Icon, CarParking02Icon, WarehouseIcon, ArrowReloadVerticalIcon, CraneIcon, BankIcon, PetrolPumpIcon, Tree06Icon, MedicineBottle01Icon, MetroIcon, Bus01Icon, Backpack01Icon, Hospital01Icon } from '@hugeicons/core-free-icons'

import AccessItem from '../../components/AccessItem.vue'
import AdvCard from '../../components/AdvCard.vue'
import AdvTitle from '../../components/AdvTitle.vue'
import AI from '../../components/AI.vue'
import CardTitle from '../../components/CardTitle.vue'
import Gallery from '../../components/Gallery.vue'
import InfoItem from '../../components/InfoItem.vue'
import Payment from '../../components/Payment.vue'
import PriceCompare from '../../components/PriceCompare.vue'
import SectionTitle from '../../components/SectionTitle.vue'
import AdvBadge from '../../components/ui/AdvBadge.vue'
import LinkButton from '../../components/ui/LinkButton.vue'
import adv1 from '../assets/files/adv/adv1.jpg'
import adv2 from '../assets/files/adv/adv2.jpg'
import adv3 from '../assets/files/adv/adv3.jpg'
import champion from '../assets/files/images/champion.svg'
import diamond from '../assets/files/images/diamond.svg'
import gold from '../assets/files/images/gold.svg'
import platinum from '../assets/files/images/platinum.svg'
import silver from '../assets/files/images/silver.svg'

</script>