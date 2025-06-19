<template>
  <section class="section">
    <h2>Ashram Progress</h2>
    <div class="ashrams">
      <div v-for="ashram in ashrams" :key="ashram.name" class="ashram-card">
        <h3>{{ ashram.name }}</h3>
        <img :src="ashram.image" alt="Ashram Image" />
        <div class="progress-wrapper" @mouseenter="hovered = ashram.name" @mouseleave="hovered = null">
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
  { name: 'Mahudi', progress: 33, remaining: '1.2 Cr', image: 'https://via.placeholder.com/300x150' },
  { name: 'Ajmer', progress: 47, remaining: '80 L', image: 'https://via.placeholder.com/300x150' }
]
</script>

<style scoped>
.section {
  padding: 3rem 2rem;
}
.ashrams {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}
.ashram-card {
  width: 300px;
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
