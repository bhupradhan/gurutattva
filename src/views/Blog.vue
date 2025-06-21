<template>
  <section class="section blog-section" id="blog">
    <h2>Divine Teachings & Stories</h2>
    <div class="blog-grid">
      <div v-for="blog in blogs" :key="blog.title" class="blog-card">
        <h3>{{ blog.title }}</h3>
        <p class="snippet">{{ blog.snippet }}</p>
        <button @click="readBlog(blog.title)">Read More</button>
      </div>
    </div>
  </section>
</template>


<script setup>
const blogs = [
  {
    title: 'Meditation: Path to Peace',
    snippet: 'Discover Swamiji’s timeless guidance on true meditation and its role in achieving inner balance.'
  },
  {
    title: 'Seeker’s Journey',
    snippet: 'A heartfelt story of a disciple who experienced spiritual transformation through Seva and surrender.'
  },
  {
    title: 'AI & Spirituality: Bridging the Inner and Outer Worlds',
    snippet: 'Exploring how artificial intelligence and spiritual wisdom can together enhance consciousness.'
  }
]

function readBlog(title) {
  alert(`Coming soon: Full blog on "${title}"`);
}
</script>

<style scoped>
.blog-section {
  background: #f9f9f9;
  padding: 4rem 2rem;
  text-align: center;
}
.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}
.blog-card {
  background: white;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
  text-align: left;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.blog-card h3 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  color: #4a148c;
}
.snippet {
  font-size: 0.95rem;
  color: #444;
  flex-grow: 1;
}
button {
  margin-top: 1rem;
  background: #6a1b9a;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  cursor: pointer;
  transition: background 0.3s ease;
}
button:hover {
  background: #4a148c;
}
</style>

