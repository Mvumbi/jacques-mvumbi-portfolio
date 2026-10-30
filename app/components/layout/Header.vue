<script setup lang="ts">
const localePath = useLocalePath()
const open = ref(false)

const links = [
  { key: 'about', hash: '#about' },
  { key: 'skills', hash: '#skills' },
  { key: 'projects', hash: '#projects' },
  { key: 'contact', hash: '#contact' },
]
</script>

<template>
  <header class="sticky top-0 z-50 border-b border-slate-200 bg-white/80 backdrop-blur dark:border-slate-800 dark:bg-slate-950/80">
    <div class="mx-auto flex h-16 max-w-6xl items-center justify-between px-4">
      <NuxtLink :to="localePath('/')" class="text-lg font-bold">
        Jacques<span class="text-brand-500">.dev</span>
      </NuxtLink>

      <nav class="hidden items-center gap-6 md:flex">
        <NuxtLink
          v-for="l in links"
          :key="l.key"
          :to="localePath({ path: '/', hash: l.hash })"
          class="text-sm font-medium text-slate-600 transition hover:text-brand-600 dark:text-slate-300 dark:hover:text-brand-400"
        >
          {{ $t(`nav.${l.key}`) }}
        </NuxtLink>
      </nav>

      <div class="flex items-center gap-2">
        <UiLangSwitcher />
        <UiThemeToggle />
        <button
          type="button"
          class="flex h-9 w-9 items-center justify-center rounded-lg border border-slate-200 md:hidden dark:border-slate-700"
          aria-label="Menu"
          @click="open = !open"
        >
          <Icon :name="open ? 'lucide:x' : 'lucide:menu'" size="18" />
        </button>
      </div>
    </div>

    <nav v-if="open" class="border-t border-slate-200 px-4 py-3 md:hidden dark:border-slate-800">
      <NuxtLink
        v-for="l in links"
        :key="l.key"
        :to="localePath({ path: '/', hash: l.hash })"
        class="block py-2 text-sm font-medium"
        @click="open = false"
      >
        {{ $t(`nav.${l.key}`) }}
      </NuxtLink>
    </nav>
  </header>
</template>