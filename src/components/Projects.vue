<template>
  <section id="projects" class="py-20 bg-white">
    <div class="max-w-6xl mx-auto px-6">
      <h2 class="text-3xl font-bold text-center mb-12">
        My Projects
      </h2>

      <div class="grid md:grid-cols-3 gap-8">
        <!-- Project Card -->
        <div
          v-for="project in projects"
          :key="project.title"
          class="border rounded-xl p-6 hover:shadow-lg transition"
        >
          <h3 class="text-xl font-semibold mb-2">
            {{ project.title }}
          </h3>

          <p class="text-gray-600 mb-4">
            {{ project.description }}
          </p>

          <span class="text-sm text-blue-500 font-medium">
            {{ project.tech }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Portfolio Website',
    description: 'Website portfolio pribadi menggunakan Vue & Tailwind CSS.',
    tech: 'Vue • Tailwind'
  },
  {
    title: 'Landing Page',
    description: 'Landing page responsive untuk tugas kampus.',
    tech: 'HTML • CSS'
  },
  {
    title: 'Robot Arm Project',
    description: 'Proyek robot tangan menggunakan mikrokontroler.',
    tech: 'Arduino • C++'
  }
]
</script>