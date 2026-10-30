<script setup lang="ts">
useHead({ htmlAttrs: { class: 'scroll-smooth' } })
</script>

<template>
  <div class="min-h-screen bg-white text-slate-900 antialiased dark:bg-slate-950 dark:text-slate-100">
    <LayoutHeader />
    <main>
      <NuxtPage />
    </main>
    <LayoutFooter />
  </div>
</template>