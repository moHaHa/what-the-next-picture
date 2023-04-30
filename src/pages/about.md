---
title: About
---

<div class="text-center">
  <!-- You can use Vue components inside markdown -->
  <div i-carbon-dicom-overlay class="text-4xl -mb-6 m-auto" />
  <h3>About</h3>
  <h4>"What The Next Picture"</h4>
  <p title="What The Next Picture">
   Simple Website for Brows, Copy or Download images, where you let the magic of Unsplash random Inspired you ✨
  </p>
</div>

```js
await fetch('https://source.unsplash.com/random/?inspire')
  .then((response) => {
    document.body.style.backgroundImage = `url('${response.url}')`
  })
  .catch((error) => {
    console.error('Error:', error)
  })
```
