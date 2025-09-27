<template>
    <div class="fixed inset-0 flex justify-end bg-black/50 z-30">
        <div class=" bg-white p-4 w-full h-full md:w-96 border-r border-r-gray-300 ">
            <div class="flex flex-col justify-between h-full">
                <div>
                    <ModalTitle :show-logo="true" />
                    <ul>
                        <li>
                            <MenuLink title="درخواست گزارش میدانی" />
                        </li>
                        <li>
                            <MenuLink title="درباره ما" />
                        </li>
                        <li>
                            <MenuLink title="تماس با ما" />
                        </li>
                        <li>
                            <MenuLink title="همکاری با اُکازیون" />
                        </li>
                        <li>
                            <MenuLink title="بلاگ" />
                        </li>
                        <li>
                            <MenuLink title="قوانین و مقررات" class="border-b-0" />
                        </li>
                    </ul>
                </div>
                <LinkButton :show-icon="false" class="w-full justify-center md:hidden" title="اُکازیون ها" />
            </div>
        </div>
    </div>
</template>

<script setup>
import MenuLink from './MenuLink'
import ModalTitle from './ModalTitle'
import LinkButton from './ui/LinkButton'
</script>
