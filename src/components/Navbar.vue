<template>
  <nav class="navbar fixed top-0 left-0 w-full bg-white shadow z-50">
    <div class="max-w-6xl mx-auto flex justify-between items-center px-6 py-4">

      <!-- Logo -->
      <div class="flex items-center gap-2 cursor-pointer" @click="scrollToTop">
        <img :src="polbanLogo" alt="Polban Logo" class="h-12 w-auto" />
      </div>

      <!-- Desktop Menu -->
      <ul class="hidden md:flex gap-6">
        <li v-for="link in links" :key="link.id">
          <a
            href="javascript:void(0)"
            @click="scrollToSection(link.id)"
            :class="[
              'nav-item transition-colors',
              activeSection === link.id
                ? 'font-bold text-white bg-purple-600 px-3 py-1 rounded'
                : 'font-medium text-purple-600'
            ]"
          >
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
    <ul
      v-if="menuOpen"
      class="mobile-menu flex flex-col gap-4 px-6 py-4 bg-white shadow md:hidden"
    >
      <li v-for="link in links" :key="link.id">
        <a
          href="javascript:void(0)"
          @click="scrollToSection(link.id); menuOpen = false"
          :class="[
            'nav-item',
            activeSection === link.id
              ? 'font-bold text-white bg-purple-600 px-3 py-1 rounded'
              : 'font-medium text-purple-600'
          ]"
        >
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
const activeSection = ref('hero')

const links = [
  { name: 'Home', id: 'hero' },
  { name: 'About and Skills', id: 'about' },
  { name: 'Projects', id: 'projects' },
  { name: 'Assignments', id: 'assignments' },
  { name: 'Contact', id: 'contact' },
]

// Scroll to section
const scrollToSection = (id) => {
  const el = document.getElementById(id)
  if (!el) return

  const offset = -80
  const y = el.getBoundingClientRect().top + window.pageYOffset + offset

  window.scrollTo({
    top: y,
    behavior: 'smooth',
  })

  activeSection.value = id
}

// Scroll to top
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

// Detect active section on scroll
const handleScroll = () => {
  const scrollPos = window.scrollY + 100

  for (const link of links) {
    const el = document.getElementById(link.id)
    if (
      el &&
      el.offsetTop <= scrollPos &&
      el.offsetTop + el.offsetHeight > scrollPos
    ) {
      activeSection.value = link.id
      return
    }
  }
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

ul {
  list-style: none;
  margin: 0;
  padding: 0;
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