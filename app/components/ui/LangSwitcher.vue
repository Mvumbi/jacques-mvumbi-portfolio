<script setup lang="ts">
const { locale } = useI18n()
const switchLocalePath = useSwitchLocalePath()
const langs = ['fr', 'en'] as const
</script>

<template>
  <div class="flex items-center gap-1 rounded-lg border border-slate-200 p-1 text-xs font-semibold dark:border-slate-700">
    <NuxtLink
      v-for="l in langs"
      :key="l"
      :to="switchLocalePath(l)"
      class="rounded-md px-2 py-1 transition"
      :class="locale === l
        ? 'bg-brand-600 text-white'
        : 'text-slate-600 hover:bg-slate-100 dark:text-slate-300 dark:hover:bg-slate-800'"
    >
      {{ l.toUpperCase() }}
    </NuxtLink>
  </div>
</template>