<template>
  <section id="projects" class="py-20 bg-slate-50">
    <div class="max-w-6xl mx-auto px-6">
      <h2 class="text-3xl font-bold mb-10 text-center">
        Projects
      </h2>

      <div class="grid md:grid-cols-3 gap-6">
        <div
          v-for="(project, index) in projects"
          :key="index"
          class="relative bg-white rounded-xl p-6 shadow
                transition hover:-translate-y-2 hover:shadow-lg"
        >
          <!-- Progress -->
          <div class="absolute top-4 right-4">
            <circle-progress
              :size="55"
              :progress="project.progress"
              :stroke-width="6"
              :fill="false"
              :empty-stroke="'#e5e7eb'"
              :stroke="'#3b82f6'"
            />
          </div>

          <!-- Title -->
          <h3 class="font-semibold text-lg mb-2">
            {{ project.title }}
          </h3>

          <!-- Description -->
          <p class="text-sm text-gray-600 mb-4">
            {{ project.desc }}
          </p>

          <!-- Tech Stack -->
          <div class="flex flex-wrap gap-2 mb-4">
            <span
              v-for="tech in project.tech"
              :key="tech"
              class="text-xs bg-blue-100 text-blue-600 px-2 py-1 rounded"
            >
              {{ tech }}
            </span>
          </div>

          <!-- Link -->
          <a
            :href="project.link"
            target="_blank"
            class="text-blue-500 text-sm hover:underline"
          >
            Lihat Detail →
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: "Tugas Besar Menghitung Jumlah Emisi Karbon dengan Bahasa C",
    desc: "Program berbasis CLI menggunakan bahasa C sebagai tugas besar semester 1.",
    tech: ["C", "CLI", "Algorithm"],
    link: "https://github.com/fironsahuleka2007-art/tugasbesarsem1ddp",
    progress: 100,
  },
  {
    title: "Website Portfolio",
    desc: "Website portfolio pribadi menggunakan Vue dan Tailwind CSS.",
    tech: ["Vue", "Tailwind", "Cloudflare"],
    link: "https://8b29552d.portfolio-vue-77d.pages.dev",
    progress: 75,
  },
]
</script>