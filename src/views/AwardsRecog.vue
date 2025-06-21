<template>
  <section class="section awards-section" id="awards">
    <h2 class="section-title">Awards & Recognition</h2>
    <h3>This is just a sample not real text</h3>
    <div class="awards-grid">
      <div v-for="award in awards" :key="award.title" class="award-card">
        <div class="award-image-wrapper">
          <!-- <img :src="award.image" alt="Award Image" class="award-image" /> -->
        </div>
        <div class="award-content">
          <h3>{{ award.title }}</h3>
          <p>{{ award.details }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const awards = [
  {
    title: 'Spiritual Excellence Award',
    details: 'Presented by Gujarat Govt, 2022',
    image: '/awards/spiritual-excellence.jpg'
  },
  {
    title: 'Global Peace Contributor',
    details: 'By International Meditation Forum, 2021',
    image: '/awards/global-peace.jpg'
  },
  {
    title: 'Lifetime Dedication to Seva',
    details: 'By Indian Spiritual Council, 2020',
    image: '/awards/lifetime-seva.jpg'
  }
]
</script>

<style scoped>
.awards-section {
  background: linear-gradient(to bottom, #e8f5e9, #ffffff);
  padding: 4rem 2rem;
  text-align: center;
}

.section-title {
  font-size: 2.5rem;
  color: #2e7d32;
  margin-bottom: 2rem;
}

.awards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 2rem;
  justify-content: center;
}

.award-card {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 1rem;
}

.award-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.12);
}

.award-image-wrapper {
  width: 100%;
  height: 180px;
  overflow: hidden;
  border-bottom: 1px solid #eee;
}

.award-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.award-content {
  padding: 1rem;
}

.award-content h3 {
  margin: 0.5rem 0;
  font-size: 1.2rem;
  color: #00695c;
}

.award-content p {
  font-size: 0.95rem;
  color: #555;
}
</style>
