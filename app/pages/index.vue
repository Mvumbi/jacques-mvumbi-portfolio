<template>
  <div>
    <section class="mx-auto flex min-h-[80vh] max-w-6xl flex-col justify-center px-4">
      <p class="font-medium text-brand-600 dark:text-brand-400">{{ $t('hero.greeting') }}</p>
      <h1 class="mt-2 text-4xl font-bold sm:text-6xl">Jacques Mvumbi</h1>
      <h2 class="mt-3 text-xl text-slate-600 sm:text-2xl dark:text-slate-300">{{ $t('hero.role') }}</h2>
      <p class="mt-6 max-w-2xl text-slate-600 dark:text-slate-400">{{ $t('hero.tagline') }}</p>
      <div class="mt-8 flex gap-3">
        <a href="#projects" class="rounded-lg bg-brand-600 px-5 py-3 text-sm font-semibold text-white transition hover:bg-brand-700">
          {{ $t('hero.cta_projects') }}
        </a>
        <a href="#contact" class="rounded-lg border border-slate-300 px-5 py-3 text-sm font-semibold transition hover:bg-slate-100 dark:border-slate-700 dark:hover:bg-slate-800">
          {{ $t('hero.cta_contact') }}
        </a>
      </div>
    </section>

    <section id="about" class="min-h-[50vh]" />
    <section id="skills" class="min-h-[50vh]" />
    <section id="projects" class="min-h-[50vh]" />
    <section id="contact" class="min-h-[50vh]" />
  </div>
</template>