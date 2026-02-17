<template>
  <section id="contact" class="contact-section">
    <!-- HEADER -->
    <div class="header">
      <h2><span>Kontak</span> Saya</h2>
      <p>Hubungi saya melalui media sosial berikut</p>
    </div>

    <!-- CARDS -->
    <div class="cards">
      <!-- GitHub -->
      <a
        href="https://github.com/fironsahuleka2007-art"
        target="_blank"
        class="card"
      >
        <div class="icon dark">
          <!-- GitHub SVG -->
          <svg viewBox="0 0 24 24">
            <path
              fill="white"
              d="M12 .297c-6.63 0-12 5.373-12 12
              0 5.303 3.438 9.8 8.205 11.385
              .6.113.82-.258.82-.577
              0-.285-.01-1.04-.015-2.04
              -3.338.724-4.042-1.415-4.042-1.415
              -.546-1.387-1.333-1.756-1.333-1.756
              -1.086-.743.084-.728.084-.728
              1.205.084 1.838 1.236 1.838 1.236
              1.07 1.835 2.809 1.305 3.495.998
              .108-.776.418-1.305.762-1.605
              -2.665-.3-5.466-1.332-5.466-5.93
              0-1.31.468-2.381 1.235-3.222
              -.123-.303-.535-1.523.117-3.176
              0 0 1.008-.322 3.3 1.23
              .957-.266 1.983-.399 3-.404
              1.02.005 2.047.138 3 .404
              2.292-1.552 3.3-1.23 3.3-1.23
              .653 1.653.241 2.873.118 3.176
              .77.841 1.235 1.912 1.235 3.222
              0 4.61-2.807 5.625-5.479 5.921
              .43.372.823 1.102.823 2.222
              0 1.606-.014 2.898-.014 3.293
              0 .319.216.694.825.576
              C20.565 22.092 24 17.592 24 12.297
              24 5.67 18.627.297 12 .297z"
            />
          </svg>
        </div>
        <h3>GitHub</h3>
        <p>@fironsahuleka2007-art</p>
      </a>

      <!-- Instagram -->
      <a
        href="https://www.instagram.com/frnshlk"
        target="_blank"
        class="card"
      >
        <div class="icon ig">IG</div>
        <h3>Instagram</h3>
        <p>@frnshlk</p>
      </a>

      <!-- WhatsApp -->
      <a
        href="https://wa.me/62895385588900"
        target="_blank"
        class="card"
      >
        <div class="icon wa">WA</div>
        <h3>WhatsApp</h3>
        <p>+62 895-3855-8890</p>
      </a>

      <!-- LinkedIn -->
      <a
        href="https://www.linkedin.com/in/firon-fariz-sahuleka-926481372/"
        target="_blank"
        class="card"
      >
        <div class="icon li">in</div>
        <h3>LinkedIn</h3>
        <p>Firon Fariz</p>
      </a>
    </div>

    <!-- EMAIL -->
    <div class="email-box">
      <h4>Email</h4>
      <p>firon.fariz.tif425@polban.ac.id</p>
      <span>Feel free to reach out!</span>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  min-height: 100vh;
  padding: 6rem 2rem;
  background: linear-gradient(180deg,#1e3a8a,#2563eb);
  color: white;
  font-family: 'Poppins', sans-serif;
}

.header {
  text-align: center;
  margin-bottom: 4rem;
}

.header h2 {
  font-size: 2.6rem;
}
.header span {
  color: #facc15;
}

.cards {
  max-width: 1000px;
  margin: auto;
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
  gap: 2rem;
}

.card {
  background: white;
  color: #1f2937;
  border-radius: 20px;
  padding: 2rem;
  text-align: center;
  text-decoration: none;
  transition: 0.35s;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0,0,0,.25);
}

.icon {
  width: 64px;
  height: 64px;
  margin: auto auto 1rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  color: white;
}

.dark { background:#111827 }
.ig { background:linear-gradient(135deg,#f58529,#dd2a7b,#8134af) }
.wa { background:#22c55e }
.li { background:#2563eb }

.email-box {
  max-width: 700px;
  margin: 5rem auto 0;
  padding: 2rem;
  border-radius: 20px;
  background: rgba(255,255,255,.15);
  text-align: center;
}
.email-box h4 { color:#facc15 }
</style>