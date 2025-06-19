<template>
  <section class="section" id="blog">
    <h2>Divine Teachings & Stories</h2>
    <ul>
      <li v-for="blog in blogs" :key="blog.title">
        <strong>{{ blog.title }}</strong> — {{ blog.snippet }}
      </li>
    </ul>
  </section>
</template>

<script setup>
const blogs = [
  { title: 'Meditation: Path to Peace', snippet: 'Discover Swamiji’s guidance on true meditation...' },
  { title: 'Seeker’s Journey', snippet: 'A disciple shares his transformation through Seva.' }
]
</script>

<style scoped>
.section {
  padding: 3rem 2rem;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  margin-bottom: 1rem;
}
</style>
