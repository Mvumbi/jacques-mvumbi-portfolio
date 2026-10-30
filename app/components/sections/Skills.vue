<script setup lang="ts">
import { skillCategories } from '~/data/skills'
</script>

<template>
  <section id="skills" class="scroll-mt-20 bg-slate-50 py-20 dark:bg-slate-900/50">
    <div class="mx-auto max-w-6xl px-4">
      <UiSectionHeading :title="$t('skills.title')" :subtitle="$t('skills.subtitle')" />

      <div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
        <article
          v-for="cat in skillCategories"
          :key="cat.key"
          class="rounded-xl border border-slate-200 bg-white p-6 dark:border-slate-800 dark:bg-slate-950"
        >
          <header class="mb-4 flex items-center gap-3">
            <span class="flex h-10 w-10 items-center justify-center rounded-lg bg-brand-500/10 text-brand-600 dark:text-brand-400">
              <Icon :name="cat.icon" size="20" />
            </span>
            <h3 class="font-semibold">{{ $t(`skills.categories.${cat.key}`) }}</h3>
          </header>

          <ul class="flex flex-wrap gap-2">
            <li
              v-for="item in cat.items"
              :key="item"
              class="rounded-md bg-slate-100 px-2.5 py-1 text-xs font-medium text-slate-700 dark:bg-slate-800 dark:text-slate-300"
            >
              {{ item }}
            </li>
          </ul>
        </article>
      </div>
    </div>
  </section>
</template>