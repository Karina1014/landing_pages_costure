<template>
  <div class="w-full h-[100vh] flex items-center justify-center bg-white overflow-hidden">

    <!-- Contenedor general estilo Meta CON ANIMACIÓN DE ENTRADA -->
    <div class="flex gap-4 rotate-[-3deg] gallery-enter">

      <!-- ==== COLUMNA 1 ==== -->
      <div class="w-[200px] h-[110vh] overflow-hidden [--duration:52s] [--gap:1rem]">
        <div class="animate-meta-marquee flex flex-col gap-[var(--gap)] marquee-start">
          <template v-for="n in 2">
            <div
              v-for="(item, i) in col1"
              :key="'c1-'+n+i"
              class="bg-white p-1.5 rounded-xl shadow-lg w-full h-[200px] overflow-hidden flex-shrink-0"
            >
              <!-- IMAGEN -->
              <img
                v-if="item.type === 'img'"
                :src="item.src"
                class="object-cover w-full h-full rounded-lg"
              />

              <!-- VIDEO -->
              <video
                v-else
                :src="item.src"
                autoplay muted loop playsinline
                class="object-cover w-full h-full rounded-lg"
              ></video>
            </div>
          </template>
        </div>
      </div>

      <!-- ==== COLUMNA 2 ==== -->
      <div class="w-[200px] h-[110vh] overflow-hidden [--duration:56s] [--gap:1rem]">
        <div class="animate-meta-marquee flex flex-col gap-[var(--gap)] marquee-start">
          <template v-for="n in 2">
            <div
              v-for="(item, i) in col2"
              :key="'c2-'+n+i"
              class="bg-white p-1.5 rounded-xl shadow-lg w-full h-[200px] overflow-hidden flex-shrink-0"
            >
              <!-- IMAGEN -->
              <img
                v-if="item.type === 'img'"
                :src="item.src"
                class="object-cover w-full h-full rounded-lg"
              />

              <!-- VIDEO -->
              <video
                v-else
                :src="item.src"
                autoplay muted loop playsinline
                class="object-cover w-full h-full rounded-lg"
              ></video>
            </div>
          </template>
        </div>
      </div>

      <!-- ==== COLUMNA 3 ==== -->
      <div class="w-[200px] h-[110vh] overflow-hidden [--duration:38s] [--gap:1rem]">
        <div class="animate-meta-marquee flex flex-col gap-[var(--gap)] marquee-start">
          <template v-for="n in 2">
            <div
              v-for="(item, i) in col3"
              :key="'c3-'+n+i"
              class="bg-white p-1.5 rounded-xl shadow-lg w-full h-[200px] overflow-hidden flex-shrink-0"
            >
              <!-- IMAGEN -->
              <img
                v-if="item.type === 'img'"
                :src="item.src"
                class="object-cover w-full h-full rounded-lg"
              />

              <!-- VIDEO -->
              <video
                v-else
                :src="item.src"
                autoplay muted loop playsinline
                class="object-cover w-full h-full rounded-lg"
              ></video>
            </div>
          </template>
        </div>
      </div>

    </div>
  </div>
</template>


<script setup>
import video1 from "@/assets/services/cociendoMaquina.mp4";

const col1 = [
  { type: "img", src: new URL('@/assets/home/homeNegocio.jpeg', import.meta.url).href },
  { type: "img", src: new URL('@/assets/home/arreglo.jpeg', import.meta.url).href },
  { type: "video", src: video1 },
  { type: "img", src: new URL('@/assets/home/colagador.jpeg', import.meta.url).href },
];

const col2 = [
  { type: "img", src: new URL('@/assets/home/costura5.gif', import.meta.url).href },
  { type: "video", src: video1 },
  { type: "img", src: new URL('@/assets/home/colagador.jpeg', import.meta.url).href },
  { type: "img", src: new URL('@/assets/home/costura3.png', import.meta.url).href },
];

const col3 = [
  { type: "img", src: new URL('@/assets/home/arreglov1.jpeg', import.meta.url).href },
  { type: "img", src: new URL('@/assets/home/arreglo.jpeg', import.meta.url).href },
];
</script>


<style scoped>
/* ===========================================
   ANIMACIÓN DE ENTRADA (AL HACER F5)
=========================================== */
@keyframes galleryFadeIn {
  0% {
    opacity: 0;
    transform: translateY(80px) scale(0.95);
  }
  100% {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.gallery-enter {
  animation: galleryFadeIn 1s ease-out forwards;
}

/* ===========================================
   DELAY PARA ACTIVAR EL MARQUEE DESPUÉS DE LA ENTRADA
=========================================== */
.marquee-start {
  animation-play-state: paused;
  animation-delay: 1s;
  animation-fill-mode: both;
}

/* ===========================================
   ANIMACIÓN VERTICAL
=========================================== */
@keyframes meta-marquee {
  0% { transform: translateY(0); }
  100% { transform: translateY(-50%); }
}

.animate-meta-marquee {
  animation: meta-marquee var(--duration) linear infinite;
}
</style>