<template>
  <section class="section">
    <h2>Gallery</h2>
    <div class="gallery">
      <img v-for="img in images" :key="img" :src="img" alt="Gallery image" />
    </div>
  </section>
</template>

<script setup>
const images = [
  'https://via.placeholder.com/250',
  'https://via.placeholder.com/250',
  'https://via.placeholder.com/250'
]
</script>

<style scoped>
.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}
.gallery img {
  width: 250px;
  height: auto;
  border-radius: 10px;
}
</style>
