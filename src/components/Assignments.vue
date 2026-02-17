<template>
<section class="py-20 bg-slate-50 min-h-screen">
    <div class="max-w-5xl mx-auto px-6">
    <!-- HEADER -->
    <div class="text-center mb-14">
        <h1 class="text-4xl font-bold mb-3 text-slate-800">
        Assignments
        <p class="text-sm text-slate-500 mt-3">
        Total tugas: {{ assignments.length }}
        </p>
        </h1>
    </div>

    <!-- ASSIGNMENT LIST -->
    <div class="space-y-6">
        <div
        v-for="(item, index) in assignments"
        :key="index"
        class="assignment-card rounded-xl p-6 shadow-sm
        transition duration-300 border-l-4
        hover:shadow-md fade-up"
        :style="{ animationDelay: `${index * 120}ms` }"
    :class="item.status === 'Selesai'
    ? 'border-blue-500'
    : 'border-yellow-400'">

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
    class="px-4 py-2 text-sm rounded-lg
        bg-blue-600 text-white
        hover:bg-blue-700 transition"
>
    Repository
</a>

<a
    v-if="item.doc"
    :href="item.doc"
    target="_blank"
    class="px-4 py-2 text-sm rounded-lg
        bg-white border border-slate-300
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
    title: "Dokumen TOR Proyek",
    course: "Penugasan 2",
    type: "Dokumen",
    desc: "Penyusunan dokumen Terms of Reference sebagai perencanaan awal proyek.",
    tools: ["Word", "PDF"],
    status: "Proses",
    repo: null,
    doc: "#",
},
{
    title: "Infografis UI/UX",
    course: "Penugasan 3",
    type: "Infografis",
    desc: "Infografis konsep UI/UX dasar sebagai latihan visual komunikasi.",
    tools: ["Canva"],
    status: "Proses",
    repo: null,
    doc: "#",
},
{
    title: "Video Kreatif",
    course: "Penugasan 4",
    type: "Video Kreatif",
    desc: "Pembuatan video kreatif untuk menunjukkan kemampuan desain dan komunikasi visual.",
    tools: ["Capcut"],
    status: "Proses",
    repo: null,
    doc: "#",
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