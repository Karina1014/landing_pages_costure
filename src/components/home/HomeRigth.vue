<template>
  <div v-if="isMobile" class="mobile-gallery">
    <!-- VERSIÓN MÓVIL: SWIPER CAROUSEL -->
    <div class="w-full h-screen flex flex-col items-center justify-center bg-white">
      <div class="w-full px-4">
        
        <!-- CONTENEDOR SWIPER -->
        <div class="w-full rounded-2xl shadow-xl overflow-hidden bg-white">
          <div class="w-full h-96 relative">
            <!-- IMAGEN/VIDEO ACTUAL -->
            <img
              v-if="allItems[currentIndex].type === 'img'"
              :src="allItems[currentIndex].src"
              :alt="`slide-${currentIndex}`"
              class="w-full h-full object-cover"
            />

            <video
              v-else
              :src="allItems[currentIndex].src"
              autoplay
              muted
              loop
              playsinline
              class="w-full h-full object-cover"
            ></video>

            <!-- BOTÓN ANTERIOR -->
            <button
              @click="prevSlide"
              class="absolute left-2 top-1/2 transform -translate-y-1/2 bg-white/80 hover:bg-white rounded-full p-2 z-10"
            >
              <svg class="w-5 h-5 text-gray-800" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
              </svg>
            </button>

            <!-- BOTÓN SIGUIENTE -->
            <button
              @click="nextSlide"
              class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-white/80 hover:bg-white rounded-full p-2 z-10"
            >
              <svg class="w-5 h-5 text-gray-800" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
              </svg>
            </button>
          </div>
        </div>

        <!-- INDICADORES (DOTS) -->
        <div class="flex gap-2 mt-4 justify-center">
          <button
            v-for="(item, i) in allItems"
            :key="`dot-${i}`"
            @click="currentIndex = i"
            :class="[
              'h-2 rounded-full transition-all',
              currentIndex === i
                ? 'bg-purple-600 w-6'
                : 'bg-gray-300 w-2'
            ]"
          ></button>
        </div>
      </div>
    </div>
  </div>

  <div v-else class="desktop-gallery">
    <!-- VERSIÓN DESKTOP: COLUMNAS VERTICALES CON ANIMACIÓN -->
    <div class="w-full h-[100vh] flex items-center justify-center bg-white overflow-hidden">
      <div class="flex gap-4 rotate-[-3deg] gallery-enter">

        <!-- ==== COLUMNA 1 ==== -->
        <div class="w-[200px] h-[110vh] overflow-hidden [--duration:52s] [--gap:1rem]">
          <div class="animate-meta-marquee flex flex-col gap-[var(--gap)] marquee-start">
            <template v-for="n in 2">
              <div
                v-for="(item, i) in col1"
                :key="'c1-' + n + i"
                class="bg-white p-1.5 rounded-xl shadow-lg w-full h-[200px] overflow-hidden flex-shrink-0"
              >
                <img
                  v-if="item.type === 'img'"
                  :src="item.src"
                  class="object-cover w-full h-full rounded-lg"
                />
                <video
                  v-else
                  :src="item.src"
                  autoplay
                  muted
                  loop
                  playsinline
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
                :key="'c2-' + n + i"
                class="bg-white p-1.5 rounded-xl shadow-lg w-full h-[200px] overflow-hidden flex-shrink-0"
              >
                <img
                  v-if="item.type === 'img'"
                  :src="item.src"
                  class="object-cover w-full h-full rounded-lg"
                />
                <video
                  v-else
                  :src="item.src"
                  autoplay
                  muted
                  loop
                  playsinline
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
                :key="'c3-' + n + i"
                class="bg-white p-1.5 rounded-xl shadow-lg w-full h-[200px] overflow-hidden flex-shrink-0"
              >
                <img
                  v-if="item.type === 'img'"
                  :src="item.src"
                  class="object-cover w-full h-full rounded-lg"
                />
                <video
                  v-else
                  :src="item.src"
                  autoplay
                  muted
                  loop
                  playsinline
                  class="object-cover w-full h-full rounded-lg"
                ></video>
              </div>
            </template>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
import video1 from '@/assets/services/cociendoMaquina.mp4'

const isMobile = ref(false)
const currentIndex = ref(0)

// Datos de columnas
const col1 = [
  { type: 'img', src: new URL('@/assets/home/homeNegocio.jpeg', import.meta.url).href },
  { type: 'img', src: new URL('@/assets/home/arreglo.jpeg', import.meta.url).href },
  { type: 'video', src: video1 },
  { type: 'img', src: new URL('@/assets/home/colagador.jpeg', import.meta.url).href },
]

const col2 = [
  { type: 'img', src: new URL('@/assets/home/costura5.gif', import.meta.url).href },
  { type: 'video', src: video1 },
  { type: 'img', src: new URL('@/assets/home/colagador.jpeg', import.meta.url).href },
  { type: 'img', src: new URL('@/assets/home/costura3.png', import.meta.url).href },
]

const col3 = [
  { type: 'img', src: new URL('@/assets/home/arreglov1.jpeg', import.meta.url).href },
  { type: 'img', src: new URL('@/assets/home/arreglo.jpeg', import.meta.url).href },
]

// Combinar todos los items para móvil
const allItems = computed(() => [...col1, ...col2, ...col3])

// Funciones de navegación
const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % allItems.value.length
}

const prevSlide = () => {
  currentIndex.value = (currentIndex.value - 1 + allItems.value.length) % allItems.value.length
}

// Detectar si es móvil
const checkMobile = () => {
  isMobile.value = window.innerWidth < 768
}

onMounted(() => {
  checkMobile()
  window.addEventListener('resize', checkMobile)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkMobile)
})
</script>

<style scoped>
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

.marquee-start {
  animation-play-state: paused;
  animation-delay: 1s;
  animation-fill-mode: both;
}

@keyframes meta-marquee {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-50%);
  }
}

.animate-meta-marquee {
  animation: meta-marquee var(--duration) linear infinite;
}
</style>