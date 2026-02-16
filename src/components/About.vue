<script setup>
const skills = [
  {
    title: "Web Development",
    desc: "Mampu membangun tampilan website menggunakan HTML, CSS, dan JavaScript serta memahami dasar framework frontend seperti Vue.",
    icon: "fas fa-code",
    color: "#6c63ff"
  },
  {
    title: "UI/UX Design",
    desc: "Memahami dasar desain antarmuka yang user-friendly, konsistensi layout, dan penggunaan warna yang nyaman untuk meningkatkan pengalaman pengguna.",
    icon: "fas fa-pen-nib",
    color: "#f1c40f"
  },
  {
    title: "Problem Solving",
    desc: "Terbiasa mencari solusi saat menemukan error dalam kode dan mampu menganalisis masalah secara logis.",
    icon: "fas fa-lightbulb",
    color: "#6c63ff"
  },
  {
    title: "Continuous Learning",
    desc: "Memiliki kemauan belajar tinggi terhadap permasalahan dan juga mencoba untuk terus mengembangkan kemampuan teknis maupun non-teknis.",
    icon: "fas fa-book",
    color: "#f1c40f"
  },
  {
    title: "Team Collaboration",
    desc: "Mampu bekerja dalam tim, berkomunikasi dengan baik, dan bertanggung jawab terhadap tugas.",
    icon: "fas fa-users",
    color: "#6c63ff"
  },
]
</script>

<template>
  <section id="about" class="py-20 bg-gray-50">
    <div class="max-w-6xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
      
      <!-- Text -->
      <div>
        <h2 class="text-3xl font-bold mb-4">About Me</h2>
        <p class="text-gray-600 mb-4">
          Saya merupakan mahasiswa Teknik Informatika Politeknik Negeri Bandung yang memiliki ketertarikan pada bidang pengembangan teknologi. Saya senang mempelajari hal baru, memecahkan masalah, serta bekerja secara teamwork sehingga semua pekerjaan dapat diselesaikan dengan baik. Saya percaya bahwa kemampuan untuk terus belajar dan beradaptasi dengan lingkungan yang ada.
        </p>
        <p class="text-gray-600">
          Selain itu, saya juga tertarik untuk aktif dalam kegiatan organisasi karena saya percaya kemampuan kerja sama tim, komunikasi, dan kepemimpinan merupakan hal penting untuk pengembangan diri dan karier di masa depan. Melalui keikutsertaan dalam himpunan, saya berharap dapat berkontribusi sekaligus mengembangkan kemampuan teknis dan soft skill saya.
        </p>
      </div>

      <!-- Skills -->
      <div class="grid gap-6">
        <div v-for="skill in skills" :key="skill.title" class="bg-white rounded-lg p-4 shadow hover:scale-105 transition-transform duration-300">
          <div :style="{ color: skill.color }" class="text-2xl mb-2">
            <i :class="skill.icon"></i>
          </div>  
          <h3 class="font-semibold text-lg mb-1">{{ skill.title }}</h3>
          <p class="text-sm text-gray-600">{{ skill.desc }}</p>
        </div>
      </div>

    </div>
  </section>
</template>