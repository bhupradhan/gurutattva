<template>
  <footer class="footer">
    <!-- Contact Form -->
    <div class="footer-section contact-form">
      <h3>Contact Us</h3>
      <form @submit.prevent="submitForm">
        <input v-model="name" placeholder="Your Name" required />
        <input v-model="email" type="email" placeholder="Your Email" required />
        <textarea v-model="message" placeholder="Message" required></textarea>
        <button type="submit">Send</button>
      </form>
    </div>

    <!-- Ashram & Contact Info -->
    <div class="footer-section info">
      <h3>Ashram Details</h3>
      <p>📍 Location: Shree Gurushaktidham Ashram, [Generic Location]</p>
      <p>📞 Contact: +91-XXXXXXXXXX</p>
    </div>

    <!-- Social Media + Quick Links -->
    <div class="footer-section links">
      <h3>Connect with Us</h3>
      <div class="social-icons">
        <a href="#" target="_blank" title="Facebook">📘</a>
        <a href="#" target="_blank" title="Instagram">📸</a>
        <a href="#" target="_blank" title="YouTube">▶️</a>
        <a href="#" target="_blank" title="Telegram">📲</a>
      </div>

      <div class="quick-links">
        <p><a href="#">Terms of Use</a> | <a href="#">Privacy Policy</a> | <a href="#">Volunteer</a></p>
        <p class="placeholder-links">[Future Links Here]</p>
      </div>
    </div>

    <!-- Footer Bottom -->
    <div class="footer-bottom">
      <p>&copy; {{ new Date().getFullYear() }} Gurutattva Foundation. All Rights Reserved.</p>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
const name = ref('')
const email = ref('')
const message = ref('')

function submitForm() {
  alert(`Thank you ${name.value}, we’ll get in touch!`)
}
</script>

<style scoped>
.footer {
  background: #f5f5f5;
  padding: 4rem 2rem 2rem;
  color: #333;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  font-family: 'Segoe UI', sans-serif;
  border-top: 2px solid #0077cc;
}

.footer-section h3 {
  margin-bottom: 1rem;
  color: #0077cc;
}

.contact-form form {
  display: flex;
  flex-direction: column;
}
.contact-form input,
.contact-form textarea {
  margin-bottom: 0.75rem;
  padding: 0.75rem;
  border-radius: 6px;
  border: 1px solid #ccc;
}
.contact-form button {
  background: #0077cc;
  color: white;
  border: none;
  padding: 0.8rem;
  border-radius: 6px;
  cursor: pointer;
}
.contact-form button:hover {
  background: #005fa3;
}

.social-icons a {
  font-size: 1.5rem;
  margin-right: 1rem;
  text-decoration: none;
}
.quick-links a {
  text-decoration: none;
  color: #0077cc;
}
.quick-links a:hover {
  text-decoration: underline;
}
.placeholder-links {
  margin-top: 0.5rem;
  font-style: italic;
  color: #777;
}

.footer-bottom {
  grid-column: 1 / -1;
  text-align: center;
  margin-top: 2rem;
  border-top: 1px solid #ddd;
  padding-top: 1rem;
  font-size: 0.9rem;
  color: #666;
}
</style>
