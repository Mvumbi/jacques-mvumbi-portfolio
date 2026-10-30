<script setup lang="ts">
const year = new Date().getFullYear()
</script>

<template>
  <footer class="border-t border-slate-200 py-8 dark:border-slate-800">
    <div class="mx-auto flex max-w-6xl flex-col items-center justify-between gap-4 px-4 text-sm text-slate-500 sm:flex-row">
      <p>© {{ year }} Jacques Mvumbi. {{ $t('footer.rights') }}</p>
      <div class="flex items-center gap-4">
        <a href="https://github.com/JacquesMvumbi" target="_blank" rel="noopener" aria-label="GitHub">
          <Icon name="lucide:github" size="20" />
        </a>
        <a href="https://www.linkedin.com/" target="_blank" rel="noopener" aria-label="LinkedIn">
          <Icon name="lucide:linkedin" size="20" />
        </a>
      </div>
    </div>
  </footer>
</template>