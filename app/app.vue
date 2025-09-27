<template>
  <div class="container mx-auto p-4 min-h-screen flex flex-col justify-between" dir="rtl">
    <!-- Header -->
    <Header />
    <!-- Main Content -->
    <main>
      <NuxtPage />
    </main>
    <!-- Footer -->
    <Footer />
  </div>
</template>

<script setup lang="ts">
// Import custom CSS
import "../assets/css/main.css";
import Footer from "../components/Footer.vue";
import Header from "../components/Header.vue";

// Global SEO meta
useSeoMeta({
  title: "Nuxt 4 Starter Kit - Production Ready",
  ogTitle: "Nuxt 4 Starter Kit - Production Ready",
  description:
    "A production-grade Nuxt 4 starter kit with TypeScript, Tailwind CSS v4, and modern tooling",
  ogDescription:
    "A production-grade Nuxt 4 starter kit with TypeScript, Tailwind CSS v4, and modern tooling",
  ogImage: "/og-image.jpg",
  twitterCard: "summary_large_image",
});
</script>
