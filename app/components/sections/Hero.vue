<script setup lang="ts">
const { locale } = useI18n()

const cvPath = computed(() =>
  locale.value === 'en'
    ? '/cv/Jacques-Mvumbi-CV-EN.pdf'
    : '/cv/Jacques-Mvumbi-CV-FR.pdf'
)

const stack = ['Vue.js', 'Nuxt', 'Tailwind CSS', 'TypeScript', 'Node.js', 'REST APIs']

const socials = [
  { name: 'GitHub', icon: 'lucide:github', url: 'https://github.com/JacquesMvumbi' },
  { name: 'LinkedIn', icon: 'lucide:linkedin', url: 'https://www.linkedin.com/in/votre-profil' },
  { name: 'Email', icon: 'lucide:mail', url: 'mailto:votre-email@exemple.com' },
]

const photoFailed = ref(false)
</script>

<template>
  <section class="relative overflow-hidden">
    <!-- décor discret -->
    <div class="pointer-events-none absolute -top-32 right-0 h-96 w-96 rounded-full bg-brand-500/20 blur-3xl" />

    <div class="relative mx-auto grid min-h-[85vh] max-w-6xl items-center gap-12 px-4 py-16 md:grid-cols-[1.4fr_1fr]">
      <!-- texte -->
      <div>
        <span class="animate-fade-up inline-flex items-center gap-2 rounded-full border border-emerald-500/30 bg-emerald-500/10 px-3 py-1 text-xs font-medium text-emerald-600 dark:text-emerald-400">
          <span class="h-2 w-2 rounded-full bg-emerald-500" />
          {{ $t('hero.available') }}
        </span>

        <p class="animate-fade-up mt-6 font-medium text-brand-600 [animation-delay:100ms] dark:text-brand-400">
          {{ $t('hero.greeting') }}
        </p>
        <h1 class="animate-fade-up mt-2 text-4xl font-bold tracking-tight [animation-delay:200ms] sm:text-6xl">
          Jacques Mvumbi
        </h1>
        <h2 class="animate-fade-up mt-3 text-xl text-slate-600 [animation-delay:300ms] sm:text-2xl dark:text-slate-300">
          {{ $t('hero.role') }}
        </h2>
        <p class="animate-fade-up mt-6 max-w-xl text-slate-600 [animation-delay:400ms] dark:text-slate-400">
          {{ $t('hero.tagline') }}
        </p>

        <div class="animate-fade-up mt-8 flex flex-wrap gap-3 [animation-delay:500ms]">
          <a href="#projects" class="rounded-lg bg-brand-600 px-5 py-3 text-sm font-semibold text-white transition hover:bg-brand-700">
            {{ $t('hero.cta_projects') }}
          </a>
          <a :href="cvPath" download class="inline-flex items-center gap-2 rounded-lg border border-slate-300 px-5 py-3 text-sm font-semibold transition hover:bg-slate-100 dark:border-slate-700 dark:hover:bg-slate-800">
            <Icon name="lucide:download" size="16" />
            {{ $t('hero.cta_cv') }}
          </a>
        </div>

        <ul class="animate-fade-up mt-8 flex flex-wrap gap-2 [animation-delay:600ms]">
          <li
            v-for="tech in stack"
            :key="tech"
            class="rounded-md bg-slate-100 px-2.5 py-1 text-xs font-medium text-slate-700 dark:bg-slate-800 dark:text-slate-300"
          >
            {{ tech }}
          </li>
        </ul>

        <div class="animate-fade-up mt-8 flex items-center gap-4 [animation-delay:700ms]">
          <a
            v-for="s in socials"
            :key="s.name"
            :href="s.url"
            target="_blank"
            rel="noopener"
            :aria-label="s.name"
            class="text-slate-500 transition hover:text-brand-600 dark:hover:text-brand-400"
          >
            <Icon :name="s.icon" size="22" />
          </a>
        </div>
      </div>

      <!-- photo -->
      <div class="animate-fade-up flex justify-center [animation-delay:300ms]">
        <div class="animate-float relative">
          <div class="absolute -inset-2 rounded-3xl bg-gradient-to-tr from-brand-500 to-purple-500 opacity-60 blur-lg" />
          <div class="relative h-72 w-72 overflow-hidden rounded-3xl border border-slate-200 bg-slate-100 sm:h-80 sm:w-80 dark:border-slate-700 dark:bg-slate-800">
            <NuxtImg
              v-if="!photoFailed"
              src="/images/jacques.jpg"
              alt="Jacques Mvumbi"
              width="320"
              height="320"
              class="h-full w-full object-cover"
              @error="photoFailed = true"
            />
            <div v-else class="flex h-full w-full items-center justify-center text-6xl font-bold text-brand-500">
              JM
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>