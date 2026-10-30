<script setup lang="ts">
defineProps<{ title: string; subtitle?: string }>()
</script>

<template>
  <div class="mb-10">
    <h2 class="text-3xl font-bold tracking-tight sm:text-4xl">
      {{ title }}
      <span class="mt-2 block h-1 w-16 rounded bg-brand-500" />
    </h2>
    <p v-if="subtitle" class="mt-4 text-slate-600 dark:text-slate-400">{{ subtitle }}</p>
  </div>
</template>