<template>
  <div class="min-h-screen bg-background">
    <!-- Header -->
    <header class="border-b border-border bg-card">
      <div class="container mx-auto px-4 py-6">
        <div class="flex items-center justify-between">
          <div class="flex items-center gap-2">
            <Icon name="logos:nuxt-icon" size="24" class="text-primary" />
            <span class="font-bold text-lg">Nuxt 4</span>
          </div>
          <nav class="flex items-center gap-4">
            <NuxtLink to="/" class="text-sm font-medium hover:text-primary">
              Home
            </NuxtLink>
            <NuxtLink
              to="/about"
              class="text-sm font-medium hover:text-primary"
            >
              About
            </NuxtLink>
            <NuxtLink
              to="/test"
              class="text-sm font-medium hover:text-primary"
            >
              Test
            </NuxtLink>
          </nav>
        </div>
      </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto px-4 py-8">
      <NuxtPage />
    </main>

    <!-- Footer -->
    <footer class="border-t border-border bg-card mt-16">
      <div class="container mx-auto px-4 py-8">
        <div class="flex items-center justify-between">
          <div class="flex items-center gap-4">
            <Icon name="logos:nuxt-icon" size="20" class="text-primary" />
            <span class="text-sm text-muted-foreground">
              Built with Nuxt 4 & Tailwind CSS
            </span>
          </div>
          <div class="flex items-center gap-4">
            <NuxtLink
              to="/about"
              class="text-sm text-muted-foreground hover:text-primary"
            >
              About
            </NuxtLink>
            <a
              href="https://github.com"
              class="text-sm text-muted-foreground hover:text-primary"
            >
              GitHub
            </a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
// Import custom CSS
import "../assets/css/main.css";

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
