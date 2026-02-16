<template>
  <nav class="navbar fixed top-0 left-0 w-full bg-white shadow z-50">
    <div class="max-w-6xl mx-auto flex justify-between items-center px-6 py-4">

      <!-- Logo -->
      <div class="flex items-center gap-2 cursor-pointer" @click="scrollToTop">
        <img :src="polbanLogo" alt="Polban Logo" class="h-12 w-auto"/>
      </div>

      <!-- Desktop Menu -->
      <ul class="nav-links hidden md:flex gap-6">
        <li v-for="link in links" :key="link.name">
          <a :href="link.href"
             :class="[
               'nav-item transition-colors',
               activeSection === link.href ? 'font-bold text-white bg-purple-600 px-3 py-1 rounded' : 'font-medium text-purple-600'
             ]">
            {{ link.name }}
          </a>
        </li>
      </ul>

      <!-- Hamburger -->
      <div class="hamburger flex flex-col gap-1 md:hidden" @click="menuOpen = !menuOpen">
        <span :class="{ open: menuOpen }"></span>
        <span :class="{ open: menuOpen }"></span>
        <span :class="{ open: menuOpen }"></span>
      </div>
    </div>

    <!-- Mobile Menu -->
    <ul v-if="menuOpen"
        class="mobile-menu flex flex-col gap-4 mt-2 px-6 py-4 bg-white shadow md:hidden">
      <li v-for="link in links" :key="link.name">
        <a :href="link.href"
           @click="menuOpen=false"
           :class="[
             'nav-item block',
             activeSection === link.href ? 'font-bold text-white bg-purple-600 px-3 py-1 rounded' : 'font-medium text-purple-600'
           ]">
          {{ link.name }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import polbanLogo from '../assets/polban.png'

const menuOpen = ref(false)
const activeSection = ref('#hero')

const links = [
  { name: 'Home', href: '#hero' },
  { name: 'About and Skills', href: '#about' },
  { name: 'Portfolio', href: '#projects' },
  { name: 'Contact', href: '#contact' },
]

const scrollToTop = () => window.scrollTo({ top: 0, behavior: 'smooth' })

// detect active section
const handleScroll = () => {
  const scrollPos = window.scrollY + 80 // offset navbar
  let found = false
  for (const link of links) {
    const el = document.querySelector(link.href)
    if (el && el.offsetTop <= scrollPos && el.offsetTop + el.offsetHeight > scrollPos) {
      activeSection.value = link.href
      found = true
      break
    }
  }
  if (!found) activeSection.value = ''
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.navbar {
  font-family: 'Poppins', sans-serif;
  backdrop-filter: blur(6px);
  transition: all 0.3s ease;
}

/* Desktop & mobile nav item */
.nav-item {
  transition: all 0.3s ease;
  list-style: none;
}

.nav-item:hover {
  color: #4b47c5;
  list-style: none;
}

/* Hamburger */
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
  z-index: 40;
}
</style>