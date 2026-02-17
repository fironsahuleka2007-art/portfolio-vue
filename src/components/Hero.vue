<template>
  <section id="hero" class="hero">
    <div class="hero-text">
      <h1>Hi! I'm Firon</h1>
      <p>Mahasiswa Teknik Informatika Politeknik Negeri Bandung</p>
      <p>HIMAKOM 40</p>
      <p>I am passionate about developing user-friendly digital solutions and continuously learning new technologies. I enjoy creating interactive web experiences and collaborating in team environments to build meaningful technology projects.</p>
      <button class="btn" @click="scrollToAssignments">See My Assignments</button>
    </div>
    <div class="hero-img">
    <img src="../assets/firon.jpeg" alt="Firon Profile" />
    </div>
  </section>
</template>

<script setup>
function scrollToAssignments() {
  const el = document.getElementById("assignments");
  if (el) el.scrollIntoView({ behavior: "smooth" });
}
</script>

<style scoped>
.hero {
  min-height: calc(100vh - 80px);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 4rem 2rem;
  background: linear-gradient(135deg,#a29bfe,#6c63ff);
  color: #fff;
  font-family: 'Poppins', sans-serif;
  border-radius: 20px;
  gap: 2rem;
  scroll-margin-top: 80px;
}

.hero-text h1 {
  font-size: 2.5rem;
  margin-bottom: 0.8rem;
  line-height: 1.2;
  font-weight: 700;
}

.hero-text p {
  font-size: 1.1rem;
  margin-bottom: 1.5rem;
  opacity: 0.9;
}

.btn {
  background: #fff;
  color: #6c63ff;
  padding: 0.8rem 1.8rem;
  border-radius: 12px;
  font-weight: 600;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

.btn:hover {
  background: #e0dfff;
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.25);
}

.hero-img img {
  width: 280px;
  border-radius: 20px;
  box-shadow: 0 15px 25px rgba(0,0,0,0.2);
  transition: transform 0.3s ease;
}

.hero-img img:hover {
  transform: rotate(-2deg) scale(1.05);
}

/* Responsive */
@media(max-width:768px){
  .hero {
    flex-direction: column;
    text-align: center;
  }
  .hero-img img { width: 220px; margin-top: 2rem; }
}
</style>