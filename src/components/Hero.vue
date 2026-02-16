<script setup>
import Navbar from "./Navbar.vue"
</script>

<template>
  <Navbar />

  <section class="min-h-screen flex items-center">
    <div class="max-w-6xl mx-auto px-6 pt-24">
      <p class="text-sm text-gray-500 mb-3">
        <span class="text-yellow-400 font-semibold">Highlight</span>
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
      <body class="bg-slate-50 text-slate-900"></body>
      <div class="mt-8 flex gap-4">
      <button class="bg-blue-900 text-white px-5 py-2 rounded-xl hover:bg-blue-800 transition">
          View Projects
      </button>

        <button class="bg-blue-900 text-white px-5 py-2 rounded-xl hover:bg-blue-800 transition">
          Contact Me
        </button>
      </div>
    </div>
  </section>
</template>