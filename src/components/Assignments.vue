<template>
<section class="py-20 bg-slate-50 min-h-screen">
    <div class="max-w-5xl mx-auto px-6">
    
    <!-- HEADER -->
    <div class="text-center mb-14">
        <h1 class="text-4xl font-bold mb-3 text-slate-800">
        Assignments
        </h1>
    </div>

    <!-- ASSIGNMENT LIST -->
    <div class="space-y-6">
        <div
        v-for="(item, index) in assignments"
        :key="index"
        class="bg-white rounded-xl p-6 shadow-sm
                border-l-4 transition
                hover:shadow-md"
        :class="item.status === 'Selesai'
            ? 'border-blue-500'
            : 'border-yellow-400'"
        >
        <!-- TOP -->
        <div class="flex flex-col md:flex-row md:items-center md:justify-between gap-4">
            <div>
            <h3 class="text-lg font-semibold text-slate-800">
                {{ item.title }}
            </h3>
            <p class="text-sm text-slate-500">
                {{ item.course }} • {{ item.type }}
            </p>
            </div>

            <!-- STATUS -->
            <span
            class="text-xs font-medium px-3 py-1 rounded-full w-fit"
            :class="item.status === 'Selesai'
                ? 'bg-blue-100 text-blue-600'
                : 'bg-yellow-100 text-yellow-700'"
            >
            {{ item.status }}
            </span>
        </div>

        <!-- DESC -->
        <p class="text-sm text-slate-600 mt-4 max-w-3xl">
            {{ item.desc }}
        </p>

        <!-- TOOLS -->
        <div class="flex flex-wrap gap-2 mt-4">
            <span
            v-for="tool in item.tools"
            :key="tool"
            class="text-xs bg-slate-100 text-slate-600 px-2 py-1 rounded"
            >
            {{ tool }}
            </span>
        </div>

        <!-- ACTION -->
        <div class="flex gap-3 mt-6">
            <a
            v-if="item.repo"
            :href="item.repo"
            target="_blank"
            class="px-4 py-2 text-sm rounded-md
                    bg-blue-500 text-white
                    hover:bg-blue-600 transition"
            >
            Repository
            </a>

            <a
            v-if="item.doc"
            :href="item.doc"
            target="_blank"
            class="px-4 py-2 text-sm rounded-md
                    border border-slate-300
                    text-slate-700
                    hover:bg-slate-100 transition"
            >
            Dokumen
            </a>
        </div>
        </div>
    </div>

    </div>
</section>
</template>

<script setup>
const assignments = [
{
    title: "Tugas Besar Emisi Karbon",
    course: "Dasar Dasar Pemrograman",
    type: "Tugas Besar",
    desc: "Program CLI berbasis bahasa C untuk menghitung estimasi emisi karbon dari aktivitas harian.",
    tools: ["C", "CLI", "Algorithm"],
    status: "Selesai",
    repo: "https://github.com/fironsahuleka2007-art/tugasbesarsem1ddp",
    doc: null,
},
{
    title: "Dokumen TOR Proyek",
    course: "Proyek 1",
    type: "Dokumen",
    desc: "Penyusunan dokumen Terms of Reference sebagai perencanaan awal proyek.",
    tools: ["Word", "PDF"],
    status: "Selesai",
    repo: null,
    doc: "#",
},
{
    title: "Infografis UI/UX",
    course: "Proyek 1",
    type: "Infografis",
    desc: "Infografis konsep UI/UX dasar sebagai latihan visual komunikasi.",
    tools: ["Figma", "Design"],
    status: "Proses",
    repo: null,
    doc: "#",
},
]
</script>