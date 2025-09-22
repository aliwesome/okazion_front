<template>
  <div>
    <h1 class="mb-6 text-3xl font-bold">Test Page</h1>
    <p class="mb-8 text-lg text-muted-foreground">
      This is a test page to verify that Nuxt 4 routing is working correctly.
    </p>

    <div class="p-6 rounded-lg border bg-card border-border">
      <h2 class="mb-4 text-xl font-semibold">Navigation Test</h2>
      <p class="mb-4">If you can see this page, the routing is working properly!</p>

      <div class="flex gap-4">
        <NuxtLink to="/" class="text-primary hover:underline">
          ← Back to Home
        </NuxtLink>
        <NuxtLink to="/about" class="text-primary hover:underline">
          Go to About →
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
// Page-specific SEO meta
useSeoMeta({
  title: "Test - Nuxt 4 Starter Kit",
  description: "Test page to verify Nuxt 4 routing functionality",
});
</script>
