<script setup lang="ts">
defineOptions({
  name: 'IndexPage',
})
</script>

<template>
  <div>
    <div text-4xl>
      <div i-carbon-fade inline-block />
      <div py-lg />
      <Random />
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
