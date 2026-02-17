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
          class="bg-white rounded-xl overflow-hidden shadow
                cursor-pointer transition-all duration-300
                hover:-translate-y-1.5 hover:shadow-lg
                animate-card"
          :style="{ animationDelay: `${index * 120}ms` }"
        >
          <!-- IMAGE -->
          <div class="h-40 overflow-hidden">
            <img
              :src="project.image"
              :alt="project.title"
              class="w-full h-full object-cover
                    transition duration-500 hover:scale-110"
            />
          </div>

          <!-- CONTENT -->
          <div class="p-6 relative">
            <!-- Progress -->
            <div class="absolute top-4 right-4">
              <circle-progress
                :size="50"
                :progress="project.progress"
                :stroke-width="6"
                :fill="false"
                :empty-stroke="'#e5e7eb'"
                :stroke="'#3b82f6'"
              />
            </div>

            <h3 class="font-semibold text-lg mb-2">
              {{ project.title }}
            </h3>

            <p class="text-sm text-gray-600 mb-4">
              {{ project.desc }}
            </p>

            <div class="flex flex-wrap gap-2 mb-4">
              <span
                v-for="tech in project.tech"
                :key="tech"
                class="text-xs bg-blue-100 text-blue-600 px-2 py-1 rounded"
              >
                {{ tech }}
              </span>
            </div>

            <div class="flex gap-4">
  <!-- LIVE DEMO -->
  <a
    v-if="project.demo"
    :href="project.demo"
    target="_blank"
    class="text-sm text-white bg-blue-500 px-4 py-2 rounded
          hover:bg-blue-600 transition"
  >
    Live Demo
  </a>

  <!-- REPOSITORY -->
  <a
    v-if="project.repo"
    :href="project.repo"
    target="_blank"
    class="text-sm text-blue-500 border border-blue-500 px-4 py-2 rounded
          hover:bg-blue-50 transition"
  >
    Repository
  </a>
</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: "Tugas Besar Menghitung Emisi Karbon",
    desc: "Program berbasis CLI menggunakan bahasa C.",
    tech: ["C", "CLI", "Algorithm"],
    repo: "https://github.com/fironsahuleka2007-art/tugasbesarsem1ddp",
    image: "/projects/gas-emisi.png",
    progress: 100,
  },
  {
    title: "Website Portfolio",
    desc: "Website portfolio pribadi menggunakan Vue dan Tailwind CSS.",
    tech: ["Vue", "Tailwind", "Cloudflare"],
    demo: "https://8b29552d.portfolio-vue-77d.pages.dev",
    repo: "https://github.com/fironsahuleka2007-art/portfolio-vue",
    image: "/projects/portfolioNew.png",
    progress: 75,
  },
  {
    title: "Website Team Landing Page",
    desc: "Latihan frontend & UI sederhana.",
    tech: ["HTML", "CSS", "JavaScript"],
    demo: "https://fironsahuleka2007-art.github.io/teamLandingPage",
    repo: "https://github.com/fironsahuleka2007-art/teamLandingPage",
    image: "/projects/landingPage.png",
    progress: 100,
  },
]
</script>

<style scoped>
.assignment-card {
  background: linear-gradient(
    to right,
    rgba(59, 130, 246, 0.08),
    rgba(255, 255, 255, 1)
  );
}

.assignment-card:hover {
  transform: translateY(-2px);
}

.fade-up {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeUp 0.5s ease forwards;
}

@keyframes fadeUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>