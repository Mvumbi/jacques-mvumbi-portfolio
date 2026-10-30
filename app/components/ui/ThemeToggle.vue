<script setup lang="ts">
const colorMode = useColorMode()

const toggle = () => {
  colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'
}
</script>

<template>
  <button
    type="button"
    aria-label="Toggle theme"
    class="flex h-9 w-9 items-center justify-center rounded-lg border border-slate-200 text-slate-600 transition hover:bg-slate-100 dark:border-slate-700 dark:text-slate-300 dark:hover:bg-slate-800"
    @click="toggle"
  >
    <ClientOnly>
      <Icon :name="colorMode.value === 'dark' ? 'lucide:sun' : 'lucide:moon'" size="18" />
    </ClientOnly>
  </button>
</template>