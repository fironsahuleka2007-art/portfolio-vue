<template>
  <section id="contact" class="contact-section">
    <!-- HEADER -->
    <div class="header">
      <h2><span>Kontak</span> Saya</h2>
      <p>Hubungi saya melalui media sosial berikut</p>
    </div>

    <!-- CONTACT CARDS -->
    <div class="cards">
      <a
        v-for="item in contacts"
        :key="item.name"
        :href="item.link"
        target="_blank"
        class="card"
      >
        <div class="icon" :style="{ background: item.bg }">
          <component :is="item.icon" />
        </div>
        <h3>{{ item.name }}</h3>
        <p>{{ item.value }}</p>
      </a>
    </div>

    <!-- EMAIL BOX -->
    <div class="email-box">
      <h4>Email</h4>
      <p>firon.fariz.tif425@polban.ac.id</p>
      <span>Feel free to reach out!k</span>
    </div>
  </section>
</template>

<script setup>
import {
  GithubIcon,
  InstagramIcon,
  WhatsAppIcon,
  LinkedinIcon,
} from './icons'

const contacts = [
  {
    name: 'GitHub',
    value: '@fironsahuleka2007-art',
    link: 'https://github.com/fironsahuleka2007-art',
    bg: '#1f2937',
    icon: GithubIcon,
  },
  {
    name: 'Instagram',
    value: '@frnshlk',
    link: 'https://www.instagram.com/frnshlk',
    bg: 'linear-gradient(135deg,#f58529,#dd2a7b,#8134af)',
    icon: InstagramIcon,
  },
  {
    name: 'WhatsApp',
    value: '+62 895-3855-8890',
    link: 'https://wa.me/62895385588900',
    bg: '#22c55e',
    icon: WhatsAppIcon,
  },
  {
    name: 'LinkedIn',
    value: 'Firon Fariz',
    link: 'https://www.linkedin.com/in/firon-fariz-sahuleka-926481372/',
    bg: '#2563eb',
    icon: LinkedinIcon,
  },
]
</script>

<style scoped>
.contact-section {
  min-height: 100vh;
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #1e3a8a, #2563eb);
  color: white;
  font-family: 'Poppins', sans-serif;
}

.header {
  text-align: center;
  margin-bottom: 4rem;
}

.header h2 {
  font-size: 2.6rem;
  font-weight: 700;
}

.header h2 span {
  color: #facc15;
}

.header p {
  margin-top: 1rem;
  opacity: 0.85;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
  max-width: 1000px;
  margin: 0 auto;
}

.card {
  background: white;
  color: #1f2937;
  border-radius: 20px;
  padding: 2rem 1.5rem;
  text-align: center;
  text-decoration: none;
  transition: all 0.35s ease;
  box-shadow: 0 10px 25px rgba(0,0,0,0.15);
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0,0,0,0.25);
}

.icon {
  width: 64px;
  height: 64px;
  margin: 0 auto 1rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}

.icon svg {
  width: 32px;
  height: 32px;
}

.card h3 {
  font-size: 1.1rem;
  font-weight: 600;
}

.card p {
  font-size: 0.9rem;
  margin-top: 0.4rem;
  color: #64748b;
}

/* EMAIL BOX */
.email-box {
  max-width: 700px;
  margin: 5rem auto 0;
  background: rgba(255,255,255,0.15);
  backdrop-filter: blur(8px);
  border-radius: 20px;
  padding: 2rem;
  text-align: center;
}

.email-box h4 {
  color: #facc15;
  margin-bottom: 0.5rem;
}

.email-box span {
  display: block;
  margin-top: 0.7rem;
  font-size: 0.9rem;
  opacity: 0.85;
}
</style>