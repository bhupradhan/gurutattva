<template>
  <section class="section">
    <h2>Voices of Devotees</h2>
    <div class="videos">
      <iframe
        v-for="video in videos"
        :key="video"
        :src="video"
        frameborder="0"
        allowfullscreen
        width="300"
        height="200"
      ></iframe>
    </div>
  </section>
</template>

<script setup>
const videos = [
  'https://www.youtube.com/embed/dQw4w9WgXcQ', // Example
  'https://www.youtube.com/embed/3GwjfUFyY6M'
]
</script>

<style scoped>
.section {
  padding: 3rem 2rem;
  text-align: center;
}
.videos {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 1rem;
}
</style>
