<script setup>
let intervalId
const imgSrc = ref('https://source.unsplash.com/random/?space planets')
onMounted(() => {
  const storyModeEl = document.querySelector('.story-mode')
  intervalId = setInterval(async () => {
    await fetch('https://source.unsplash.com/random/?space planets')
      .then((response) => {
        imgSrc.value = response.url
      })
      .catch((error) => {
        console.error('Error:', error)
      })
  }, 5000)
})

onUnmounted(() => {
  clearInterval(intervalId)
})
</script>

<template>
  <div h-100vh flex items-center>
    <div b="1 white" h="xl:400px" w="xl:400px" mx-auto overflow-hidden rounded-full>
      <img :src="imgSrc" alt="random" h-full w-full object-cover>
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: full
</route>

<style>

</style>
