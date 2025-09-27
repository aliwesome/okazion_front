<template>
    <section class="flex flex-col justify-center items-center gap-y-4 md:gap-y-8 py-4 md:py-6">
        <!-- logo -->
        <div class="relative my-10">
            <Okazion />
        </div>
        <div class="w-full flex flex-col gap-y-4 md:w-[500px]">
            <Back title="ثبت فرم همکاری" />
            <div class="bg-white p-6 rounded-xl border border-gray-200 overflow-hidden">
                <!-- factor - #1 -->
                <div class="">
                    <PaymentMessage title="اطلاعات شما با موفقیت ثبت شد." />
                    <div class="mt-6">
                        <!-- alert -->
                        <BaseAlert title="کارشناسان اُکازیون بزودی با شما تماس میگیرند" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>


import Back from '../../components/Back.vue'
import Okazion from '../../components/Okazion.vue'
import PaymentMessage from '../../components/PaymentMessage.vue'
import BaseAlert from '../../components/ui/BaseAlert.vue'
</script>