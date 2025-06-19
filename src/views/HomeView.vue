<template>
  <div class="home-container">
    <!-- Fixed Logo -->
<nav class="navbar">
  <div class="navbar-left">
    <img src="@/assets/Gurutattva-Logo-Regi.png" alt="NGO Logo" class="logo" />
  </div>
  <div class="navbar-right">
    <a href="#gallery">Events</a>
    <a href="#gurukarya">Gurukarya</a>
    <a href="#ashramprog">Our Ashrams</a>
  </div>
</nav>

<section class="hero-section" @wheel.prevent="handleScroll">
  <!-- Fullscreen Slider with Content -->
  <div class="slider-wrapper">
    <div class="slides" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
      <!-- Slide 1: Guru Photo & Message -->
      <div class="slide guru-slide">
        <div class="guru-content">
          <img src="@/assets/swamiji2.jpg" alt="Shree Shivkrupanand Swami" class="guru-photo" />
          <div class="guru-text">
            <h1>Shree Shivkrupanand Swami</h1>
            <p>
              “Experience true inner peace through meditation.”  
              <br />
              A visionary spreading ancient wisdom for modern lives.
            </p>
          </div>
        </div>
      </div>

      <!-- Slide 2: Placeholder for your custom content -->
      <div class="slide">
        <div class="custom-content">
          <h2>Your Next Slide Title</h2>
          <p>Place your own content here — text, images, or CTA buttons.</p>
        </div>
      </div>

      <!-- Add more slides below -->
    </div>
  </div>

  <!-- Slide Indicators -->
  <div class="slide-indicators">
    <span
      v-for="(_, index) in totalSlides"
      :key="index"
      :class="{ active: index === currentSlide }"
      @click="currentSlide = index"
    ></span>
  </div>
</section>
<section id="cta" class="cta-section">
  <div class="cta-wrapper">
    <h2>Be a Part of Gurukarya</h2>
    <p>Choose your way to contribute to Swamiji's mission</p>

    <div class="cta-buttons">
      <button @click="scrollToSection('donation')">💖 Donate</button>
      <button @click="scrollToSection('blog')">📖 Lekh</button>
      <button @click="scrollToSection('contactus')">🤝 Join Us</button>
    </div>
  </div>
</section>



    <!-- Vision Mission Values -->
    <section id= 'vmv' class="vmv-section">
      <div class="vmv-title">
        <h2>Our Guiding Light</h2>
        <p>Vision • Mission • Values</p>
      </div>

      <div class="vmv-cards">
        <div class="vmv-card">
          <div class="vmv-icon">🌟</div>
          <h3>Vision</h3>
          <p>
            To empower every individual in the 21st century to live a life filled with purpose and joy.
          </p>
        </div>

        <div class="vmv-card">
          <div class="vmv-icon">🧘</div>
          <h3>Mission</h3>
          <p>
            To offer transformative global solutions that make meditation a truly captivating,
            supportive, and deeply enriching journey for everyone.
          </p>
        </div>

        <div class="vmv-card">
          <div class="vmv-icon">🤝</div>
          <h3>Values</h3>
          <p>
            We believe in learning, growing, sharing, and thriving — together.
          </p>
        </div>
      </div>
    </section>

    <!-- Dynamic Sections -->
    <section id="donation" class="section-wrapper">
      <Donation />
    </section>

    <section id="blog" class="section-wrapper">
      <Blog />
    </section>

    <section id="gallery" class="section-wrapper">
      <Gallery />
    </section>
    <section id="gurukarya" class="section-wrapper">
      <GuruKarya />
    </section><section id="ashramprog" class="section-wrapper">
      <AshramProgress />
    </section><section id="awardrecog" class="section-wrapper">
      <AwardsRecog />
    </section>
    <section id="contactus" class="section-wrapper">
      <ContactUs />
    </section>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

// Imported child sections
import Donation from './Donation.vue'
import Blog from './Blog.vue'
import ContactUs from './ContactUs.vue'
import Gallery from './Gallery.vue'
import Testimonials from './Testimonials.vue'
import GuruKarya from './GuruKarya.vue'
import AshramProgress from './AshramProgress.vue'
import AwardsRecog from './AwardsRecog.vue'

const currentSlide = ref(0)

const totalSlides = 2 // Add more as you add slides
let scrollLocked = false
//let intervalId
// onMounted(() => {
//   intervalId = setInterval(() => {
//     currentSlide.value = (currentSlide.value + 1) % images.length
//   }, 10000)
// })
// onUnmounted(() => {
//   clearInterval(intervalId)
// })


const scrollToSection = (id) => {
  const el = document.getElementById(id)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
  } else {
    console.warn(`No section found with ID: ${id}`)
  }
}

const handleScroll = (event) => {
  if (scrollLocked) return
  scrollLocked = true

  if (event.deltaY > 0) {
    // Scrolling Down
    if (currentSlide.value < totalSlides -1) {
      currentSlide.value++
    } else {
      scrollToSection('cta')
    }
  } else {
    // Scrolling Up
    if (window.scrollY < 100 && currentSlide.value > 0) {
      currentSlide.value--
    }
  }

  // Unlock scroll after short delay
  setTimeout(() => {
    scrollLocked = false
  }, 800) // Adjust delay based on transition speed
}




</script>

<style scoped>
.hero-section {
  position: relative;
  overflow: hidden;
  height: 90vh;
  width: 100%;
}

.slider-wrapper {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.slides {
  display: flex;
  transition: transform 1s ease;
  height: 100%;
}

.slide {
  min-width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #f0f8ff;
  padding: 2rem;
  box-sizing: border-box;
}

/* Guru Slide Specific */
.guru-slide {
  background: linear-gradient(to right, #fdfcfb, #e2d1c3);
}

.guru-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.guru-photo {
  max-height: 300px;
  border-radius: 12px;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.3);
  margin-bottom: 1.5rem;
}

.guru-text h1 {
  font-size: 2.5rem;
  color: #8b0000;
  margin-bottom: 0.5rem;
}

.guru-text p {
  font-size: 1.2rem;
  color: #444;
  max-width: 600px;
}

/* Placeholder slide */
.custom-content {
  text-align: center;
}

.custom-content h2 {
  font-size: 2rem;
  color: #0077cc;
}

.custom-content p {
  color: #444;
  max-width: 600px;
  margin: 1rem auto;
}

/* Indicators */
.slide-indicators {
  position: absolute;
  bottom: 50px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 12px;
  z-index: 5;
}

.slide-indicators span {
  height: 12px;
  width: 12px;
  background-color: #ccc;
  border-radius: 50%;
  cursor: pointer;
  transition: all 0.3s;
}

.slide-indicators .active {
  background-color: #0077cc;
  transform: scale(1.2);
}


/* -------------
.hero-section {
  margin-top: 80px;
  text-align: center;
  position: relative;
  overflow: hidden;
  background: #f9f9f9;
}

.slider-wrapper {
  width: 100%;
  height: 450px;
  overflow: hidden;
}

.slides {
  display: flex;
  transition: transform 1s ease;
}

.slide {
  min-width: 100%;
  height: 450px;
}

.slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.slide-indicators {
  display: flex;
  justify-content: center;
  margin: 1rem 0;
}

.slide-indicators span {
  height: 12px;
  width: 12px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  margin: 0 5px;
  transition: background-color 0.3s;
  cursor: pointer;
}

.slide-indicators .active {
  background-color: #0077cc;
  transform: scale(1.3);
}

.hero-content {
  max-width: 700px;
  margin: 0 auto;
  padding: 2rem 1rem;
  color: #333;
}

.hero-content h1 {
  font-size: 2.4rem;
  margin-bottom: 0.8rem;
}

.hero-content p {
  font-size: 1.1rem;
  line-height: 1.6;
} */

/* CTA Section */
.cta-section {
  background: linear-gradient(to right, #f5fafd, #e6f3ec);
  padding: 4rem 2rem;
  text-align: center;
}

.cta-wrapper {
  max-width: 800px;
  margin: 0 auto;
}

.cta-wrapper h2 {
  font-size: 2rem;
  color: #0077cc;
  margin-bottom: 0.5rem;
}

.cta-wrapper p {
  font-size: 1.1rem;
  color: #444;
  margin-bottom: 2rem;
}

.cta-buttons {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 1.5rem;
}

.cta-buttons button {
  padding: 0.9rem 1.7rem;
  background-color: #0077cc;
  color: white;
  font-size: 1rem;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s ease;
}

.cta-buttons button:hover {
  background-color: #005fa3;
}



.home-container {
  font-family: 'Segoe UI', sans-serif;
  color: #333;
  position: relative;
}

/* Fixed Logo */
.fixed-logo {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  padding: 1rem;
  background: white;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}
.logo {
  height: 50px;
}

/* Hero Section */
.hero-section {
  margin-top: 80px;
  position: relative;
}
.slider {
  width: 100%;
  height: 500px;
  overflow: hidden;
}
.slides {
  display: flex;
  transition: transform 1s ease;
}
.slide {
  min-width: 100%;
  height: 500px;
}
.slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.hero-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: white;
  text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.6);
  background: rgba(0, 0, 0, 0.3);
  padding: 2rem;
  border-radius: 12px;
}
.hero-content h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}
.hero-content p {
  font-size: 1.1rem;
  max-width: 800px;
  margin: 0 auto 2rem;
}
.cta-buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
}
.cta-buttons button {
  padding: 0.75rem 1.5rem;
  background: #0077cc;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 1rem;
  cursor: pointer;
  transition: background 0.3s ease;
}
.cta-buttons button:hover {
  background: #005fa3;
}

/* Vision-Mission-Values */
.vmv-section {
  background: linear-gradient(to bottom, #f5f7fa, #e0f7f3);
  padding: 4rem 2rem;
  text-align: center;
}
.vmv-title h2 {
  font-size: 2.2rem;
  margin-bottom: 0.5rem;
  color: #004c3f;
}
.vmv-title p {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 3rem;
}
.vmv-cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
}
.vmv-card {
  background: white;
  border-radius: 12px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.05);
  padding: 2rem;
  max-width: 320px;
  flex: 1 1 280px;
  transition: transform 0.3s ease;
}
.vmv-card:hover {
  transform: translateY(-5px);
}
.vmv-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}
.vmv-card h3 {
  color: #007f6e;
  font-size: 1.4rem;
  margin-bottom: 0.5rem;
}
.vmv-card p {
  color: #444;
  font-size: 1rem;
  line-height: 1.6;
}

/* Section Wrapper */
.section-wrapper {
  padding: 4rem 2rem;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: white;
  z-index: 1000;
  padding: 0.75rem 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.navbar-left .logo {
  height: 50px;
}

.navbar-right a {
  margin-left: 1.5rem;
  text-decoration: none;
  color: #0077cc;
  font-weight: 500;
  font-size: 1rem;
  transition: color 0.3s;
}

.navbar-right a:hover {
  color: #005fa3;
}

</style>
