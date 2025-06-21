<template>
  <section id="donation" class="donation-section">
    <h2>Donate for a Cause</h2>

    <!-- Donation Blocks -->
    <div
      class="donation-block"
      v-for="(item, index) in donationItems"
      :key="index"
    >
      <div class="donation-content">
        <img :src="item.image" :alt="item.title" class="donation-image" />
        <div class="donation-text">
          <h3>{{ item.title }}</h3>
          <p>{{ item.description }}</p>
          <button @click="donateNow(item.title)">
            {{ item.buttonLabel }}
          </button>
        </div>
      </div>
    </div>

    <!-- Quote -->
    <blockquote class="quote">
      “दान का मकसद गुरुकार्य से जुड़ना है। फिर चाहे आप तन से जुड़े, मन से जुड़े या धन दे कर,
      आपका गुरुकार्य से जुड़ना महत्वपूर्ण है।”<br />
      — सदगुरु श्री शिवकृपानंद स्वामीजी
    </blockquote>
  </section>
</template>

<script setup>
const donationItems = [
  {
    title: 'Guru-Shakti Dham Nirmaan',
    image: 'Dham-Nirman.jpg',
    description:
      'Guru-Shakti Dham is a divine place to contain and grow the energies of Shree Mangal Murti. Swamiji once said, “Guru-Shakti Dham will become a centre point for the seekers around the globe and source for the self-realization.”',
    buttonLabel: 'Donate for Guru-Shakti Dham',
  },
  {
    title: 'Ashram Maintenance',
    image: 'Ashram-Maintenance06.jpg',
    description:
      'Guru Tattva Ashrams are divine places to discover one’s inner-self. While one is self-sustainable, others require Shram and Dhan-Daan to sustain. We heartily invite you to contribute for Ashram Maintenance.',
    buttonLabel: 'Donate for Ashram Maintenance',
  },
  {
    title: 'Gaushala Maintenance',
    image: 'gaushala-Maintenance02.jpg',
    description:
      'Each Ashram’s Gaushala houses Indian cows and bulls, cared for with cleanliness and nutritious food. Each Gaumata is named by Swamiji and brings spiritual grace. Join this Gurukarya by supporting Gaushalas.',
    buttonLabel: 'Donate for Gaushala',
  },
  {
    title: 'Donate directly to Swamiji',
    image: 'Donate-to-Swamiji.jpg',
    description:
      'Though Swamiji never asks for personal donations, many sadhaks wish to donate directly. These are used largely for the global Gurukarya.',
    buttonLabel: 'Donate to Swamiji',
  },
  {
    title: 'Join through Shram-Daan',
    image: 'gaushala-Maintenance04.jpg',
    description:
      'Thousands of Sadhaks donate their time for Prachaar, Ashram and Centre maintenance, and events. You can join too by becoming a volunteer or Sevadhari.',
    buttonLabel: 'Become a Sevadhari',
  },
]

function donateNow(title) {
  alert(`Thank you for your interest in "${title}". Redirecting to donation options...`)
}
</script>

<style scoped>
.donation-section {
  padding: 4rem 2rem;
  background: #fffaf0;
  text-align: center;
}

.donation-section h2 {
  font-size: 2rem;
  margin-bottom: 2.5rem;
  color: #8b0000;
}

.donation-block {
  margin-bottom: 3rem;
  max-width: 1100px;
  margin-left: auto;
  margin-right: auto;
}

.donation-content {
  display: flex;
  flex-direction: row;
  gap: 2rem;
  align-items: flex-start;
  background: #fff;
  padding: 1.5rem;
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  text-align: left;
  flex-wrap: wrap;
}

.donation-image {
  width: 100%;
  max-width: 400px;
  height: auto;
  border-radius: 10px;
  object-fit: cover;
  flex-shrink: 0;
}

.donation-text {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.donation-text h3 {
  font-size: 1.5rem;
  color: #333;
  margin-bottom: 0.5rem;
}

.donation-text p {
  font-size: 1rem;
  color: #555;
  margin-bottom: 1rem;
}

button {
  background: #c62828;
  color: white;
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 6px;
  font-size: 1rem;
  cursor: pointer;
  width: fit-content;
  transition: background 0.3s ease;
}

button:hover {
  background: #a32020;
}

.quote {
  margin-top: 4rem;
  font-style: italic;
  font-size: 1.1rem;
  color: #555;
  border-top: 1px dashed #ccc;
  padding-top: 1.5rem;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.6;
}
</style>
