<template>
  <div>
    <!-- Hero Section -->
    <section class="text-center py-12">
      <div class="flex flex-col gap-4">
        <Okazion :show-slogan="true" />
        <div class="flex flex-col justify-center items-center gap-10">
          <form action="" class="w-full md:w-[580px]">
            <BaseInput :img-src="divar" :show-button="true" variant="default" :show-image="true"
              placeholder="لینک آگهی دیوار را وارد کنید" :show-label="false" :icon="AiSearch02Icon" input-class="py-7" />
          </form>
          <!-- ADS Part -->
          <div class="flex flex-col gap-4 w-full md:w-[1024px]">
            <SectionTitle title="برترین های اُکازیون" />
            <ul
              class="flex items-center md:justify-center gap-4 md:gap-6 overflow-x-auto flex-nowrap md:flex-wrap py-2 -mx-4 px-4"
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
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { AiSearch02Icon } from '@hugeicons/core-free-icons'

import AdvCard from '../../components/AdvCard.vue'
import Okazion from '../../components/Okazion.vue'
import SectionTitle from '../../components/SectionTitle.vue'
import BaseInput from '../../components/ui/BaseInput.vue'
import adv1 from '../assets/files/adv/adv1.jpg'
import adv2 from '../assets/files/adv/adv2.jpg'
import adv3 from '../assets/files/adv/adv3.jpg'
import divar from '../assets/files/images/Divar.svg'




// Page-specific SEO meta
useSeoMeta({
  title: "اُکازیون - تحلیل ملک با AI",
  ogTitle: "Home - Nuxt 4 Starter Kit",
  description:
    "Welcome to the Nuxt 4 starter kit - a production-grade starter with TypeScript, Tailwind CSS v4, and modern tooling",
  ogDescription:
    "Welcome to the Nuxt 4 starter kit - a production-grade starter with TypeScript, Tailwind CSS v4, and modern tooling",
});
</script>
