<template>
  <section id="swamiji-journey" class="section journey-section">
    <h2>Journey of Swamiji</h2>
    <p class="journey-intro">
      Swamiji’s life is a story of deep spiritual surrender and transformation.
      From the majestic Himalayas to every heart that seeks peace, his journey has lit the path for millions.
    </p>
    <div class="journey-card">
      <img src="/About-Swamiji.jpg" alt="Swamiji in Himalayas" />
      <div class="journey-text">
        <p>
          He went to the Himalayas, lived there for 16 years, surrendered himself to the divine energy of different Himalayan Gurus,
          and absorbed the 800-year-old wisdom of meditation — just to share it with the world at no cost at all!
        </p>
        <p><em>Immerse yourself in his journey from being a seeker to a Guru!</em></p>
      </div>
    </div>
  </section>

 <section id="milestones" class="section milestones-section">
    <h2>Milestones</h2>
    <div class="timeline">
      <div
        v-for="(item, index) in milestones"
        :key="index"
        class="timeline-item"
        :class="{ left: index % 2 === 0, right: index % 2 !== 0 }"
      >
        <div class="content">
          <span class="year">{{ item.year }}</span>
          <p class="desc">{{ item.description }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- <section id="ashrams" class="section ashram-section">
    <h2>Our Global Ashrams</h2>
    <p class="intro">A glimpse into the sacred spaces where meditation and seva thrive.</p>

    <div class="ashram-grid">
      <div v-for="(ashram, index) in ashrams" :key="index" class="ashram-card">
        <img :src="ashram.image" :alt="ashram.name" />
        <h3>{{ ashram.name }}</h3>
      </div>
    </div>
  </section> -->
</template>

<script setup>
const milestones = [
  { year: '1996', description: 'First spiritual retreat conducted' },
  { year: '2001', description: 'Establishment of the first Ashram' },
  { year: '2010', description: 'Global Samarpan Meditation Movement' },
  { year: '2020', description: 'Digital Seva and Global Outreach' }
]

// const ashrams = [
//   { name: 'Dandi, Navsari', image: 'Dandi.jpg' },
//   { name: 'Punadi, Bhuj (Kutch)', image: 'kutchAshram.jpg' },
//   { name: 'Ajmer, Rajasthan', image: 'Ajmer.jpg' },
//   { name: 'Shiroda, Goa', image: 'goa.jpg' },
//   { name: 'Sindhavadar, Morbi', image: 'saurashtra.jpg' },
//   { name: 'Long Acre, UK', image: 'image-8_1.jpeg' },
//   { name: 'Saint-Colomban, Quebec', image: 'image-8_1.jpeg' }
// ]
</script>

<style scoped>
.section {
  padding: 4rem 2rem;
  text-align: center;
}

.milestones-section {
  background: #fdfdfd;
  position: relative;
}

.timeline {
  position: relative;
  max-width: 800px;
  margin: 3rem auto;
  padding: 2rem 0;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0;
  bottom: 0;
  width: 4px;
  background: #0077cc;
  transform: translateX(-50%);
}

.timeline-item {
  position: relative;
  width: 50%;
  padding: 1rem 2rem;
}

.timeline-item.left {
  left: 0;
  text-align: right;
}

.timeline-item.right {
  left: 50%;
  text-align: left;
}

.timeline-item::before {
  content: '';
  position: absolute;
  top: 1.2rem;
  width: 15px;
  height: 15px;
  background-color: #0077cc;
  border-radius: 50%;
  z-index: 1;
}

.timeline-item.left::before {
  right: -8px;
}

.timeline-item.right::before {
  left: -8px;
}

.content {
  background: #eef6ff;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.year {
  font-weight: bold;
  font-size: 1.2rem;
  color: #0077cc;
}

.desc {
  margin-top: 0.5rem;
  font-size: 1rem;
  color: #333;
}
/* Journey */
.journey-section {
  background: #fffdf6;
}
.journey-intro {
  max-width: 700px;
  margin: 0 auto 2rem;
  font-size: 1.1rem;
}
.journey-card {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
  align-items: center;
}
.journey-text {
  max-width: 500px;
  text-align: left;
}

/* Gurukarya */
.gurukarya-section {
  background: #f4faff;
  font-size: 1.1rem;
  color: #444;
}

/* Timeline */
.milestones-section {
  background: #fefefb;
}
.timeline {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 2rem;
}
.timeline-item {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
}
.year {
  font-weight: bold;
  color: #0077cc;
}
.desc {
  color: #444;
}

/* Ashram */
.ashram-section {
  background: #f9fcff;
}
.ashram-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}
.ashram-card {
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
  padding: 1rem;
}
.ashram-card img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 1rem;
}
</style>
