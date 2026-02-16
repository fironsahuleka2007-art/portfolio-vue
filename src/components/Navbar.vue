<template>
  <nav :class="['navbar fixed top-0 left-0 w-full z-50 transition-all duration-500', bgColor]">
    <div class="max-w-6xl mx-auto flex justify-between items-center px-6 py-4">

      <!-- Logo -->
      <div class="flex items-center gap-2 cursor-pointer" @click="scrollToTop">
        <img :src="polbanLogo" alt="Polban Logo" class="h-10 w-auto"/>
      </div>

      <!-- Desktop Menu -->
      <ul class="nav-links hidden md:flex gap-6">
        <li v-for="link in links" :key="link.name">
          <a :href="link.href"
            :class="['nav-item transition-colors', activeSection === link.href ? 'font-bold text-black' : 'font-normal text-purple-600']">
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
          :class="['nav-item block', activeSection === link.href ? 'font-bold text-black' : 'font-normal text-purple-600']">
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
const bgColor = ref('bg-white/90 backdrop-blur')

const links = [
  { name: 'Home', href: '#hero' },
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Portfolio', href: '#portfolio' },
  { name: 'Contact', href: '#contact' },
]

const scrollToTop = () => window.scrollTo({ top: 0, behavior: 'smooth' })

// Detect current section on scroll
const handleScroll = () => {
  const scrollPos = window.scrollY + 80 // offset for navbar height
  for (const link of links) {
    const el = document.querySelector(link.href)
    if (el && el.offsetTop <= scrollPos && el.offsetTop + el.offsetHeight > scrollPos) {
      activeSection.value = link.href
      // Ganti background sesuai section
      switch(link.href){
        case '#hero': bgColor.value = 'bg-purple-100/90 backdrop-blur'; break;
        case '#about': bgColor.value = 'bg-yellow-100/90 backdrop-blur'; break;
        case '#skills': bgColor.value = 'bg-green-100/90 backdrop-blur'; break;
        case '#portfolio': bgColor.value = 'bg-blue-100/90 backdrop-blur'; break;
        case '#contact': bgColor.value = 'bg-pink-100/90 backdrop-blur'; break;
        default: bgColor.value = 'bg-white/90 backdrop-blur';
      }
      break
    }
  }
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.navbar {
  font-family: 'Poppins', sans-serif;
  transition: background-color 0.5s ease;
}

.nav-item {
  transition: all 0.3s ease;
}

.nav-item:hover {
  color: #4b47c5;
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