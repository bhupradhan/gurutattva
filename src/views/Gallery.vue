<template>
  <section class="section">
    <h2>Events</h2>
    <div class="gallery">
      <div
        class="gallery-item"
        v-for="(img, index) in images"
        :key="index"
      >
        <img :src="img.src" :alt="img.alt" />
        <p class="caption">{{ img.caption }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
const images = [
  {
    src: 'MahaShivratri-Parv_Thumb.jpg',
    alt: 'Maha Shivratri Event',
    caption: 'Maha Shivratri Parv celebrated with divine energy and sadhaks from around the world.'
  },
  {
    src: 'Makar-Sankranti-thumb.jpg',
    alt: 'Makar Sankranti',
    caption: 'Festive gathering during Makar Sankranti at the Ashram.'
  },
  {
    src: 'Guru-Purnima-Event-2021-1-600x403.jpg',
    alt: 'Guru Purnima 2021',
    caption: 'Heartfelt Guru Purnima celebration with global participation in 2021.'
  }
]
</script>

<style scoped>
.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}

.gallery-item {
  text-align: center;
  width: 250px;
}

.gallery img {
  width: 100%;
  height: auto;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.caption {
  margin-top: 0.5rem;
  font-size: 0.95rem;
  color: #555;
}
</style>
