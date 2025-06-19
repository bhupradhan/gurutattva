<template>
  <section class="section" id="donation">
    <h2>Support the Mission</h2>
    <p>Your donations directly contribute to building Ashrams and expanding seva globally.</p>
    <button @click="donateNow">Donate Now</button>
    <p class="summary">Average Monthly Donation: ₹8,00,000</p>
    <ul class="donors">
      <li><strong>Agriculture Minister</strong> – ₹60 Lakhs for Rajkot Ashram</li>
    </ul>
  </section>
</template>

<script setup>
function donateNow() {
  alert('Redirecting to donation portal...');
}
</script>

<style scoped>
.section {
  padding: 3rem 2rem;
  background: #fff0f5;
  text-align: center;
}
button {
  background: #c62828;
  color: white;
  padding: 0.8rem 1.5rem;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
}
.summary {
  margin-top: 1rem;
  font-weight: bold;
}
.donors {
  margin-top: 1rem;
  list-style: none;
  padding: 0;
}
</style>
