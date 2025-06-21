<template>
  <section id="ashrams" class="section ashram-section">
    <h2>Ashram Progress</h2>
    <div class="ashram-grid">
      <div v-for="ashram in ashrams" :key="ashram.name" class="ashram-card">
        <h3>{{ ashram.name }}</h3>
        <img :src="ashram.image" alt="Ashram Image" />
        <div
          class="progress-wrapper"
          @mouseenter="hovered = ashram.name"
          @mouseleave="hovered = null"
        >
          <div class="progress-bar" :style="{ width: ashram.progress + '%' }"></div>
        </div>
        <div class="info">
          {{ ashram.progress }}% Complete
          <span v-if="hovered === ashram.name"> - ₹{{ ashram.remaining }} remaining</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const hovered = ref(null)

const ashrams = [
  { name: 'Dandi, Navsari', progress: 33, remaining: '1.2 Cr', image: 'Dandiashram.jpg' },
  { name: 'Punadi, Bhuj (Kutch)', progress: 47, remaining: '80 L', image: 'kutchAshram.jpg' },
  { name: 'Ajmer, Rajasthan', progress: 60, remaining: '50 L', image: 'Ajmer.jpg' },
  { name: 'Shiroda, Goa', progress: 25, remaining: '1.5 Cr', image: 'goa.jpg' },
  { name: 'Sindhavadar, Morbi', progress: 70, remaining: '30 L', image: 'saurashtra.jpg' },
  { name: 'Long Acre, UK', progress: 85, remaining: '15 L', image: 'image-8_1.jpeg' },
  { name: 'Saint-Colomban, Quebec', progress: 55, remaining: '1 Cr', image: 'image-8_1.jpeg' }
]
</script>

<style scoped>
.section {
  padding: 4rem 2rem;
  text-align: center;
}

.ashram-section {
  background: #f9fcff;
}

.ashram-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.ashram-card {
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
  padding: 1rem;
  transition: transform 0.3s ease;
}

.ashram-card:hover {
  transform: translateY(-5px);
}

.ashram-card img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 1rem;
}

.progress-wrapper {
  background: #eee;
  height: 20px;
  border-radius: 10px;
  overflow: hidden;
  margin-top: 1rem;
}

.progress-bar {
  background: #2196f3;
  height: 100%;
  transition: width 0.5s;
}

.info {
  margin-top: 0.5rem;
  font-weight: bold;
}
</style>
