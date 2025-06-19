<template>
  <section class="section">
    <h2>Join the Gurukarya</h2>
    <div class="cards">
      <div v-for="(seva, index) in sevas" :key="index" class="card">
        <h3>{{ seva.name }}</h3>
        <p>{{ seva.description }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
const sevas = [
  { name: 'Digital Seva', description: 'Help spread teachings online.' },
  { name: 'Annadan Seva', description: 'Sponsor meals at ashrams.' },
  { name: 'Ashram Volunteering', description: 'Contribute physically at locations.' }
]
</script>

<style scoped>
.section {
  padding: 3rem 2rem;
}
.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1.5rem;
}
.card {
  background: #eaf6ff;
  padding: 1.5rem;
  border-radius: 10px;
  width: 250px;
  box-shadow: 0 0 10px rgba(0,0,0,0.05);
}
</style>
