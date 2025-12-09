<template>
  <div class="w-full flex flex-col items-center py-16 bg-white">

    <!-- TÍTULO -->
    <h2 class="text-3xl font-bold text-center mb-10">Servicios</h2>

    <!-- CONTENEDOR GENERAL DEL SLIDER -->
    <div class="relative w-full max-w-6xl px-6">

      <!-- BOTÓN IZQUIERDO -->
      <button
        class="absolute left-0 top-1/2 -translate-y-1/2 z-20 w-12 h-12 bg-white rounded-full shadow-md flex items-center justify-center hover:bg-gray-100"
        @click="scrollLeft"
      >
        <span class="text-3xl leading-none">‹</span>
      </button>

     <!-- SLIDER PRINCIPAL -->
<div
  ref="slider"
  class="flex gap-6 overflow-x-auto scroll-smooth no-scrollbar px-2 py-6"
>
  <div
    v-for="(img, i) in imagesLoop"
    :key="i"
    class="min-w-[140px] sm:min-w-[180px] h-[180px] rounded-[30px] overflow-hidden shadow-lg bg-white flex-shrink-0"
  >
    <img :src="img" class="w-full h-full object-cover" />
  </div>
</div>


      <!-- BOTÓN DERECHO -->
      <button
        class="absolute right-0 top-1/2 -translate-y-1/2 z-20 w-12 h-12 bg-white rounded-full shadow-md flex items-center justify-center hover:bg-gray-100"
        @click="scrollRight"
      >
        <span class="text-3xl leading-none">›</span>
      </button>

    </div>

  </div>
</template>

<script setup>
import { ref, onMounted } from "vue"

const img1 = new URL('@/assets/home/costura1.png', import.meta.url).href
const img2 = new URL('@/assets/home/costura2.png', import.meta.url).href
const img3 = new URL('@/assets/home/costura3.png', import.meta.url).href
const img4 = new URL('@/assets/home/costura4.png', import.meta.url).href

// Loop visual como Meta
const imagesLoop = [img1, img2, img3, img4, img1, img2]

const slider = ref(null)

function scrollLeft() {
  slider.value.scrollBy({ left: -380, behavior: "smooth" })
}

function scrollRight() {
  slider.value.scrollBy({ left: 380, behavior: "smooth" })
}

// Auto-play
onMounted(() => {
  setInterval(() => {
    if (!slider.value) return
    slider.value.scrollBy({ left: 380, behavior: "smooth" })
  }, 3000)
})
</script>

<style scoped>
/* Ocultar scrollbar */
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  scrollbar-width: none;
}
</style>
