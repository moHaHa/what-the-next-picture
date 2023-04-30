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

setInterval(async () => {
  await fetch('https://source.unsplash.com/random/?space planets')
    .then((response) => {
      document.body.style.backgroundImage = `url('${response.url}')`
    })
    .catch((error) => {
      console.error('Error:', error)
    })
}, 10000)
</script>

<template>
  <RouterView />
</template>

<style>
body {
  background-image: url('https://images.unsplash.com/photo-1624358731587-7b…medium=referral&utm_source=unsplash_source&w=1080');
  background-position: center;
  background-size: contain;
  height: 100vh;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  background-repeat: no-repeat;
}
</style>
