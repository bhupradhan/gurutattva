<template>
  <section class="section">
    <h2>Awards & Recognition</h2>
    <div class="awards">
      <div v-for="award in awards" :key="award.title" class="award-card">
        <img :src="award.image" alt="Award" />
        <p><strong>{{ award.title }}</strong><br/>{{ award.details }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
const awards = [
  {
    title: 'Spiritual Excellence Award',
    details: 'Presented by Gujarat Govt, 2022',
    image: 'https://via.placeholder.com/150'
  }
]
</script>

<style scoped>
.section {
  padding: 3rem 2rem;
  background: #f5fff5;
}
.awards {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  justify-content: center;
}
.award-card {
  text-align: center;
  max-width: 200px;
}
.award-card img {
  width: 100%;
  border-radius: 8px;
}
</style>
