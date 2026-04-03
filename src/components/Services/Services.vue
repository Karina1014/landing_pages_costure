<template>
  <section id="servicios" class="w-full bg-[#FAF9FC] py-16 lg:py-24 overflow-hidden relative">
    
    <!-- Título y Encabezado (Escala Reducida) -->
    <div class="max-w-7xl mx-auto px-6 lg:px-12 mb-12 text-center">
      <div class="flex flex-col items-center gap-3">
        <span class="text-[9px] font-black uppercase tracking-[0.4em] text-[#831378] opacity-60">Excelencia en Costura</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-black text-gray-900 leading-tight tracking-tighter">
          Nuestros <span class="text-[#831378]">Servicios</span>
        </h2>
        <div class="h-[1px] w-12 bg-[#831378]/30 mt-1"></div>
      </div>
    </div>

    <!-- ======== CONTENEDOR CARRUSEL META STYLE (Compacto) ======== -->
    <div class="relative w-full">
      <Swiper
        :modules="[Navigation, Pagination, Autoplay]"
        :loop="true"
        :slides-per-view="1.25"
        :centered-slides="true"
        :space-between="20"
        :autoplay="{ delay: 5000, disableOnInteraction: false }"
        :navigation="{
          nextEl: '.nextBtn',
          prevEl: '.prevBtn'
        }"
        :pagination="{
          el: '.custom-pagination',
          clickable: true
        }"
        :breakpoints="{
          640: { slidesPerView: 1.8, spaceBetween: 30 },
          1024: { slidesPerView: 2.5, spaceBetween: 40 },
          1536: { slidesPerView: 3.2, spaceBetween: 50 }
        }"
        class="services-swiper !overflow-visible"
      >
        <SwiperSlide v-for="(item, i) in services" :key="i" v-slot="{ isActive }">
          <div 
            class="flex flex-col gap-6 transition-all duration-700"
            :class="isActive ? 'opacity-100 scale-100' : 'opacity-30 scale-90 blur-[1px]'"
          >
            <!-- Card de Imagen -->
            <div class="relative aspect-[16/11] w-full rounded-[2rem] overflow-hidden shadow-lg bg-white border border-gray-100">
              <img :src="item.img" :alt="item.name" class="w-full h-full object-cover transition-transform duration-1000" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/10 via-transparent to-transparent"></div>
              
              <!-- Badge Minimalista -->
              <div class="absolute top-4 right-4 px-3 py-1 bg-white/40 backdrop-blur-md border border-white/20 rounded-full text-white text-[8px] font-bold uppercase tracking-widest">
                Premium
              </div>
            </div>

            <!-- Información -->
            <div class="text-center px-4">
              <h3 class="text-xl lg:text-2xl font-black text-gray-900 mb-2 tracking-tight">
                {{ item.name }}
              </h3>
              <p class="text-gray-500 text-sm max-w-sm mx-auto leading-relaxed">
                {{ item.description }}
              </p>
            </div>
          </div>
        </SwiperSlide>
      </Swiper>

      <!-- Botones de Navegación (Más Pequeños) -->
      <div class="absolute top-[40%] left-0 right-0 -translate-y-1/2 flex justify-between px-2 lg:px-8 pointer-events-none z-30">
        <button class="prevBtn w-12 h-12 rounded-full bg-white/60 backdrop-blur-md border border-white/40 shadow-lg flex items-center justify-center text-gray-800 pointer-events-auto hover:bg-white transition-all duration-300">
          <ChevronLeft class="w-6 h-6" />
        </button>
        <button class="nextBtn w-12 h-12 rounded-full bg-white/60 backdrop-blur-md border border-white/40 shadow-lg flex items-center justify-center text-gray-800 pointer-events-auto hover:bg-white transition-all duration-300">
          <ChevronRight class="w-6 h-6" />
        </button>
      </div>
    </div>

    <!-- Paginación -->
    <div class="custom-pagination mt-12 flex justify-center gap-2"></div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Navigation, Autoplay } from "swiper/modules";
import { ChevronLeft, ChevronRight } from 'lucide-vue-next';

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

import img1 from "@/assets/home/costura1.png";
import img2 from "@/assets/home/costura2.png";
import img3 from "@/assets/home/costura3.png";
import img4 from "@/assets/home/costura4.png";

const services = [
  { 
    img: img1, 
    name: "Arreglos de Alta Costura",
    description: "Personalización técnica para un ajuste anatómico impecable."
  },
  { 
    img: img2, 
    name: "Diseño & Transformación",
    description: "Reimaginamos tus prendas para adaptarlas a tendencias modernas."
  },
  { 
    img: img3, 
    name: "Restauración Textil",
    description: "Cuidado artesanal para prendas dañadas, preservando su esencia."
  },
  { 
    img: img4, 
    name: "Confección sobre Medida",
    description: "Creación exclusiva basada en tus especificaciones personales."
  }
];
</script>

<style scoped>
.services-swiper {
  padding-bottom: 20px;
}

.italic-style {
  font-family: serif;
  font-style: italic;
}

:deep(.swiper-pagination-bullet) {
  width: 8px;
  height: 3px;
  border-radius: 2px;
  background: #831378;
  opacity: 0.15;
  transition: all 0.4s ease;
}

:deep(.swiper-pagination-bullet-active) {
  width: 32px;
  opacity: 1;
  background: #831378;
}

#servicios::before,
#servicios::after {
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  width: 10%;
  z-index: 20;
  pointer-events: none;
}

#servicios::before {
  left: 0;
  background: linear-gradient(to right, #FAF9FC 0%, transparent 100%);
}

#servicios::after {
  right: 0;
  background: linear-gradient(to left, #FAF9FC 0%, transparent 100%);
}
</style>