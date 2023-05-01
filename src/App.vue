<script setup lang="ts">
// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'What The Next Picture',
  meta: [
    { name: 'description', content: 'What The Next Picture is Simple Website for Brows, Copy or Download images, Where you let the magic of Unsplash random Inspired you ✨' },
    { name: 'author', content: 'Mohammad Al Hallaq' },
    { name: 'twitter:card', content: 'summary' },
    { name: 'twitter:creator', content: '@mohaha300' },
    {
      name: 'theme-color',
      content: () => isDark.value ? '#00aba9' : '#ffffff',
    },
  ],
  link: [
    {
      rel: 'icon',
      type: 'image/svg+xml',
      href: () => preferredDark.value ? '/favicon-dark.svg' : '/favicon.svg',
    },
  ],
})
</script>

<template>
  <RouterView />
</template>
