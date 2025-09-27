<template>
    <ul class="flex items-center justify-between gap-4">
        <li>
            <a href="#" class="hover:text-orange-500 transition-all">
                <HugeiconsIcon :icon="WhatsappIcon" />
            </a>
        </li>
        <li>
            <a href="#" class="hover:text-orange-500 transition-all">
                <HugeiconsIcon :icon="TelegramIcon" />
            </a>
        </li>
        <li>
            <a href="#" class="hover:text-orange-500 transition-all">
                <HugeiconsIcon :icon="InstagramIcon" />
            </a>
        </li>
        <li>
            <a href="#" class="hover:text-orange-500 transition-all">
                <HugeiconsIcon :icon="NewTwitterIcon" />
            </a>
        </li>
    </ul>
</template>

<script setup>
import { WhatsappIcon, TelegramIcon, InstagramIcon, NewTwitterIcon } from '@hugeicons/core-free-icons'
import { HugeiconsIcon } from '@hugeicons/vue'
</script>