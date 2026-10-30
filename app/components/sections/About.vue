<script setup lang="ts">
const highlights = [
  { key: 'integration', icon: 'lucide:plug' },
  { key: 'fullstack', icon: 'lucide:layers' },
  { key: 'team', icon: 'lucide:users' },
]

// Remplacez par vos vrais chiffres
const stats = [
  { key: 'years', value: '[X]+' },
  { key: 'projects', value: '[X]+' },
  { key: 'integrations', value: '[X]+' },
]
</script>

<template>
  <section id="about" class="scroll-mt-20 py-20">
    <div class="mx-auto max-w-6xl px-4">
      <UiSectionHeading :title="$t('about.title')" />

      <div class="grid gap-12 lg:grid-cols-2">
        <div class="space-y-4 text-slate-600 dark:text-slate-300">
          <p>{{ $t('about.p1') }}</p>
          <p>{{ $t('about.p2') }}</p>
          <p>{{ $t('about.p3') }}</p>

          <dl class="grid grid-cols-3 gap-4 pt-6">
            <div v-for="s in stats" :key="s.key">
              <dt class="text-3xl font-bold text-brand-600 dark:text-brand-400">{{ s.value }}</dt>
              <dd class="mt-1 text-xs text-slate-500">{{ $t(`about.stats.${s.key}`) }}</dd>
            </div>
          </dl>
        </div>

        <ul class="grid gap-4">
          <li
            v-for="h in highlights"
            :key="h.key"
            class="flex gap-4 rounded-xl border border-slate-200 p-5 transition hover:border-brand-500/50 hover:shadow-md dark:border-slate-800"
          >
            <span class="flex h-11 w-11 shrink-0 items-center justify-center rounded-lg bg-brand-500/10 text-brand-600 dark:text-brand-400">
              <Icon :name="h.icon" size="22" />
            </span>
            <div>
              <h3 class="font-semibold">{{ $t(`about.highlights.${h.key}.title`) }}</h3>
              <p class="mt-1 text-sm text-slate-600 dark:text-slate-400">
                {{ $t(`about.highlights.${h.key}.text`) }}
              </p>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>