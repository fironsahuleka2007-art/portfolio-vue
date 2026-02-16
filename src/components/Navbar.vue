<template>
  <nav class="navbar">
    <div class="logo">Firon.</div>
    <ul class="nav-links">
      <li v-for="link in links" :key="link.name">
        <a :href="link.href" class="nav-item">{{ link.name }}</a>
      </li>
    </ul>
    <div class="hamburger" @click="toggleMenu">
      <span :class="{ 'open': menuOpen }"></span>
      <span :class="{ 'open': menuOpen }"></span>
      <span :class="{ 'open': menuOpen }"></span>
    </div>
  </nav>

  <!-- Mobile menu -->
  <ul class="mobile-menu" v-if="menuOpen">
    <li v-for="link in links" :key="link.name">
      <a :href="link.href" @click="menuOpen=false">{{ link.name }}</a>
    </li>
  </ul>
</template>

<script setup>
import { ref } from 'vue'
const menuOpen = ref(false)
const links = [
  { name: 'Home', href: '#hero' },
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Portfolio', href: '#portfolio' },
  { name: 'Contact', href: '#contact' },
]
function toggleMenu() {
  menuOpen.value = !menuOpen.value
}
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  background: rgba(255,255,255,0.9);
  backdrop-filter: blur(6px);
  z-index: 100;
  font-family: 'Poppins', Tahoma;
}

.logo {
  font-weight: 700;
  font-size: 1.5rem;
  color: #6c63ff;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-item {
  color: #6c63ff;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-item:hover {
  color: #6c63ff;
}

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
}

.hamburger span {
  width: 25px;
  height: 3px;
  background: #6c63ff;
  border-radius: 3px;
  transition: all 0.3s ease;
}

.hamburger span.open:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}
.hamburger span.open:nth-child(2) {
  opacity: 0;
}
.hamburger span.open:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

/* Mobile menu */
.mobile-menu {
  display: none;
  flex-direction: column;
  gap: 1rem;
  padding: 1rem 2rem;
  background: rgba(255,255,255,0.95);
  backdrop-filter: blur(6px);
}

@media (max-width:768px){
  .nav-links { display: none; }
  .hamburger { display: flex; }
  .mobile-menu { display: flex; }
}
</style>