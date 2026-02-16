<script setup>
import Navbar from "./components/Navbar.vue"
</script>

<template>
  <Navbar />

  <section class="min-h-screen flex items-center">
    <div class="max-w-6xl mx-auto px-6 pt-24">
      <p class="text-sm text-gray-500 mb-3">
        Halo, saya Firon Fariz Sahuleka, Mahasiswa Teknik Informatika Politeknik Negeri Bandung.
      </p>

      <h1 class="text-4xl md:text-6xl font-bold leading-tight">
        Firon Fariz Sahuleka.<br />
        <span class="text-gray-400">
          I build web interfaces.
        </span>
      </h1>

      <p class="mt-6 max-w-xl text-gray-600">
        Dolor ipsum dolor sit amet, consectetur adipiscing elit. Donec vel mauris quam. Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.
      </p>

      <div class="mt-8 flex gap-4">
        <button
          class="px-6 py-3 bg-black text-white rounded-lg hover:bg-gray-800 transition"
        >
          View Projects
        </button>

        <button
          class="px-6 py-3 border border-gray-300 rounded-lg hover:bg-gray-100 transition"
        >
          Contact Me
        </button>
      </div>
    </div>
  </section>
</template>