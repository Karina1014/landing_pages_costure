<template>
  <section id="testimonios" class="py-20 bg-gray-50">
    <!-- Título -->
    <div class="text-center mb-16">
      <h2 class="text-4xl sm:text-5xl md:text-6xl font-bold mb-4">
        Lo que <span class="text-[#831378]">dicen</span> nuestros clientes
      </h2>
      <p class="text-gray-700 text-lg max-w-2xl mx-auto">
        Conoce las experiencias de quienes ya confiaron en nuestros servicios.
      </p>
    </div>

    <!-- Slider de testimonios -->
    <div class="max-w-6xl mx-auto relative">
      <Swiper
        :modules="[Pagination, Navigation]"
        :loop="true"
        :slides-per-view="1"
        :space-between="30"
        :pagination="{ el: '.swiper-pagination', clickable: true }"
        :navigation="{ nextEl: '.nextArrowBtn', prevEl: '.prevArrowBtn' }"
        :breakpoints="{
          640: { slidesPerView: 1 },
          768: { slidesPerView: 2 },
          1024: { slidesPerView: 3 }
        }"
        class="swiper"
      >
        <SwiperSlide v-for="(item, i) in testimonios" :key="i">
          <div
            class="bg-white rounded-2xl shadow-lg p-8 flex flex-col items-center text-center transition-transform duration-300 hover:scale-105"
          >
            <img
              :src="item.avatar"
              :alt="item.nombre"
              class="w-20 h-20 rounded-full mb-4 object-cover"
            />
            <p class="text-gray-700 mb-4">"{{ item.mensaje }}"</p>
            <h3 class="text-[#831378] font-bold">{{ item.nombre }}</h3>
            <span class="text-gray-500 text-sm">{{ item.empresa }}</span>
          </div>
        </SwiperSlide>
      </Swiper>

      <!-- Flechas -->
      <div class="prevArrowBtn absolute top-1/2 left-0 transform -translate-y-1/2 z-10 bg-[#831378] text-white w-10 h-10 rounded-full flex items-center justify-center cursor-pointer hover:scale-110 transition-transform">
        <i class="bx bx-chevron-left text-2xl"></i>
      </div>
      <div class="nextArrowBtn absolute top-1/2 right-0 transform -translate-y-1/2 z-10 bg-[#831378] text-white w-10 h-10 rounded-full flex items-center justify-center cursor-pointer hover:scale-110 transition-transform">
        <i class="bx bx-chevron-right text-2xl"></i>
      </div>

      <!-- Bullets -->
      <div class="swiper-pagination mt-8 flex justify-center"></div>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Navigation } from "swiper/modules";

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

// === Lista de testimonios ===
import avatar1 from "@/assets/home/persona1.png";
import avatar2 from "@/assets/home/persona2.png";
import avatar3 from "@/assets/home/persona3.png";

const testimonios = [
  {
    nombre: "Ana Martínez",
    empresa: "Diseños Creativos",
    mensaje: "Excelente servicio y atención personalizada. ¡100% recomendados!",
    avatar: avatar1,
  },
  {
    nombre: "Carlos López",
    empresa: "Moda Urbana",
    mensaje: "Mi experiencia fue increíble. La calidad es insuperable.",
    avatar: avatar2,
  },
  {
    nombre: "María Gómez",
    empresa: "Estilo y Confort",
    mensaje: "Se nota la pasión por el trabajo. Mis prendas quedaron perfectas.",
    avatar: avatar3,
  },
];
</script>

<style scoped>
/* Flechas y bullets */
.prevArrowBtn,
.nextArrowBtn {
  transition: all 0.3s ease;
}

.swiper-pagination-bullet {
  background: #831378;
  opacity: 0.4;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  margin: 0 6px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.swiper-pagination-bullet:hover {
  opacity: 0.7;
  transform: scale(1.2);
}

.swiper-pagination-bullet-active {
  background: #831378;
  opacity: 1;
  width: 14px;
  height: 14px;
  border-radius: 50%;
  box-shadow: 0 4px 15px rgba(131, 19, 120, 0.4);
}
</style>
