<template>
<nav class="navbar fixed top-0 left-0 w-full bg-white shadow z-50">
  <div class="max-w-6xl mx-auto flex justify-between items-center px-6 py-4"></div>
    <!-- Logo -->
    <div class="flex items-center gap-2 cursor-pointer" @click="scrollToTop">
      <img :src="polbanLogo" alt="Polban Logo" class="h-10 w-auto"/>
    </div>

    <!-- Desktop Menu -->
    <ul class="nav-links hidden md:flex gap-6 list-none m-0 p-0">
      <li v-for="link in links" :key="link.name" class="list-none">
        <a :href="link.href" class="nav-item">{{ link.name }}</a>
      </li>
    </ul>

    <!-- Hamburger -->
    <div class="hamburger flex flex-col gap-1 md:hidden" @click="menuOpen = !menuOpen">
      <span :class="{ open: menuOpen }"></span>
      <span :class="{ open: menuOpen }"></span>
      <span :class="{ open: menuOpen }"></span>
    </div>

    <!-- Back To Top -->
    <button
    v-show="showTopBtn"
    @click="scrollToTop"
    class="fixed bottom-6 right-6 bg-purple-600 text-white p-3 rounded-full shadow hover:bg-purple-700 transition z-[999]">
    <i class="fas fa-arrow-up"></i>
    </button>

  </nav>

  <!-- MOBILE MENU (SATU SAJA) -->
  <ul v-if="menuOpen"
    class="mobile-menu flex flex-col gap-4 mt-2 px-6 py-4 bg-white shadow md:hidden list-none m-0 p-0">
    
    <li v-for="link in links" :key="link.name" class="list-none">
      <a :href="link.href" @click="menuOpen=false">{{ link.name }}</a>
    </li>

  </ul>
</template>


<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import polbanLogo from '../assets/polban.png'

const menuOpen = ref(false)
const showTopBtn = ref(false)

const links = [
  { name: 'Home', href: '#hero' },
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Portfolio', href: '#portfolio' },
  { name: 'Contact', href: '#contact' },
]

const scrollToTop = () => window.scrollTo({ top: 0, behavior: 'smooth' })

const handleScroll = () => showTopBtn.value = window.scrollY > 300

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.navbar {
  font-family: 'Poppins', sans-serif;
  backdrop-filter: blur(6px);
  list-style: none; 
}

.nav-item {
  color: #6c63ff;
  font-weight: 500;
  list-style: none; 
  transition: color 0.3s ease;
}

.nav-item:hover {
  color: #4b47c5;
  list-style: none; 
}

.hamburger span {
  width: 25px;
  height: 3px;
  background: #6c63ff;
  border-radius: 2px;
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
  position: absolute;
  top: 70px;
  left: 0;
  width: 100%;
  background: rgba(255,255,255,0.95);
  backdrop-filter: blur(6px);
  z-index: 40;
}
</style>