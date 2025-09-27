<template>
    <header>
        <div class="flex justify-between items-center">
            <Logo />
            <div class="flex items-stretch gap-2">
                <LinkButton :show-icon="false" title="اُکازیون ها" class="hidden leading-loose md:block px-6" />
                <Button :icon="DashboardSquare01Icon" :show-title="false" variant="outline" />
            </div>
        </div>
        <!-- Menu - Desktop from left - Mobile from Bottom -->
        <Menu class="hidden" />
        <!-- breadcrumb -->
        <Breadcrumb v-if="$route.name !== 'index'" />
    </header>
</template>

<script setup>
import { DashboardSquare01Icon } from "@hugeicons/core-free-icons";

import Breadcrumb from "./Breadcrumb.vue";
import Logo from "./Logo.vue";
import Menu from "./Menu.vue";
import Button from "./ui/Button.vue";
import LinkButton from "./ui/LinkButton.vue";
</script>