<template>
  <section id="projects" class="py-20">
    <div class="max-w-6xl mx-auto px-6">
      <h2 class="text-3xl font-bold mb-10 text-center">Projects</h2>
<circle-progress
  :size="100"
  :progress="90"
  :stroke-width="8"
  :animation="true"
  :animation-duration="1000"
  :fill="false"
  :empty-stroke="'#e5e7eb'"
  :stroke="'#3b82f6'" />  
      <div class="grid md:grid-cols-3 gap-6">
        <div
          v-for="n in 3"
          :key="n"
          class="bg-white rounded-xl p-6 shadow hover:-translate-y-2 transition"
        >
          <h3 class="font-semibold text-lg mb-2">Project {{ n }}</h3>
          <p class="text-sm text-gray-600 mb-4">
            Website portfolio menggunakan Vue & Tailwind.
          </p>
          <a href="#" class="text-blue-500 text-sm hover:underline">
            Lihat Detail →
          </a>
        </div>
      </div>
    </div>
  </section>
</template>