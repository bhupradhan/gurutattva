<template>
  <section id="about" class="section">
    <h2>About Shree Shivkrupanand Swami</h2>
    <p>
      Swamiji's life has been dedicated to spreading the light of meditation and seva. From the Himalayas to modern ashrams, his journey has inspired millions worldwide.
    </p>
    <div class="timeline">
      <div v-for="(event, index) in milestones" :key="index" class="event">
        <strong>{{ event.year }}</strong>: {{ event.description }}
      </div>
    </div>
  </section>
</template>

<script setup>
const milestones = [
  { year: '1996', description: 'First spiritual retreat conducted' },
  { year: '2001', description: 'Establishment of the first ashram' },
  { year: '2020', description: 'Global digital seva mission launched' }
]
</script>

<style scoped>
.section {
  padding: 3rem 2rem;
  background: #f5faff;
  text-align: center;
}
.timeline {
  margin-top: 2rem;
}
.event {
  margin-bottom: 1rem;
}
</style>
