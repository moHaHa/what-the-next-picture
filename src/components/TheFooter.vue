<script setup lang="ts">
import { availableLocales, loadLanguageAsync } from '~/modules/i18n'

const { t, locale } = useI18n()

async function toggleLocales() {
  // change to some real logic
  const locales = availableLocales
  const newLocale = locales[(locales.indexOf(locale.value) + 1) % locales.length]
  await loadLanguageAsync(newLocale)
  locale.value = newLocale
}
</script>

<template>
  <nav flex="~ col gap-4" fixed bottom-0 right-0 mt-6 justify-center p-lg text-xl>
    <RouterLink icon-btn to="/" :title="t('button.gallery_mode')">
      <div i-carbon-fade />
    </RouterLink>
    <RouterLink icon-btn to="/story-mode" :title="t('button.story_mode')">
      <div i-carbon-circle-dash />
    </RouterLink>

    <button icon-btn :title="t('button.toggle_dark')" @click="toggleDark()">
      <div i="carbon-sun dark:carbon-moon" />
    </button>
    <div w-full b-b="1" />
    <a icon-btn rel="noreferrer" href="https://github.com/mohaha" target="_blank" title="Mohammad Al hallaq @mohaha ">
      <div i-carbon-logo-github />
    </a>

    <a v-if="false" icon-btn :title="t('button.toggle_langs')" @click="toggleLocales()">
      <div i-carbon-language />
    </a>
    <RouterLink icon-btn to="/about" :title="t('button.about')">
      <div i-carbon-dicom-overlay />
    </RouterLink>
  </nav>
</template>
