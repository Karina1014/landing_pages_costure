<template>
  <section id="cards" class="py-20 bg-gradient-to-b from-white to-gray-50">
    
    <!-- Título mejorado -->
    <div class="text-center mb-16">
      <h2 class="text-4xl sm:text-5xl md:text-6xl font-extrabold leading-tight mb-4">
        <span class="text-black">Nuestros </span>
        <span class="bg-gradient-to-r from-[#6c1a8b] to-pink-500 bg-clip-text text-transparent">
          Servicios
        </span>
      </h2>
      <p class="text-gray-600 text-lg max-w-2xl mx-auto">
        Descubre nuestra gama completa de servicios de costura y diseño
      </p>
    </div>

    <div class="main-content">
      <Swiper
        :modules="[Navigation, Pagination, EffectCoverflow]"
        :loop="true"
        :slides-per-view="3"
        :centered-slides="true"
        :space-between="50"
        :effect="'coverflow'"
        :cover-flow-effect="{
          rotate: 35,
          stretch: 100,
          depth: 400,
          modifier: 1,
          slideShadows: true
        }"
        :pagination="{
          el: '.swiper-pagination',
          clickable: true
        }"
        :navigation="{
          nextEl: '.nextArrowBtn',
          prevEl: '.prevArrowBtn'
        }"
        :breakpoints="{
          320: { slidesPerView: 1, spaceBetween: 20 },
          576: { slidesPerView: 1.5, spaceBetween: 30 },
          768: { slidesPerView: 3, spaceBetween: 50 }
        }"
        class="swiper"
      >
        <SwiperSlide v-for="(item, i) in slides" :key="i">
          <div class="slide-wrapper group">
            <img :src="item.img" :alt="item.name" class="slide-image" />
            
            <!-- Overlay con info -->
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/0 to-transparent rounded-2xl opacity-0 group-hover:opacity-100 transition-all duration-300 flex flex-col justify-end p-6">
              <h3 class="text-white text-xl font-bold mb-2">{{ item.name }}</h3>
              <p class="text-gray-200 text-sm mb-4">{{ item.description }}</p>
              <button class="bg-gradient-to-r from-[#6c1a8b] to-pink-500 text-white px-4 py-2 rounded-lg font-semibold hover:shadow-lg transition-all duration-300 w-full">
                Ver más
              </button>
            </div>
          </div>
        </SwiperSlide>
      </Swiper>

      <!-- Flechas mejoradas -->
      <div class="prevArrowBtn group">
        <i class="bx bx-chevron-left group-hover:scale-125 transition-transform duration-300"></i>
      </div>
      <div class="nextArrowBtn group">
        <i class="bx bx-chevron-right group-hover:scale-125 transition-transform duration-300"></i>
      </div>

      <!-- Bullets mejorados -->
      <div class="swiper-pagination"></div>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Navigation, EffectCoverflow } from "swiper/modules";

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/effect-coverflow";

// === Importa tus imágenes ===
import img1 from "@/assets/home/costura1.png";
import img2 from "@/assets/home/costura2.png";
import img3 from "@/assets/home/costura3.png";
import img4 from "@/assets/home/costura4.png";

// === Lista con descripciones ===
const slides = [
  { 
    img: img1, 
    name: "Arreglos Básicos",
    description: "Ajustes y modificaciones en tus prendas favoritas"
  },
  { 
    img: img2, 
    name: "Diseño Personalizado",
    description: "Crea prendas únicas diseñadas especialmente para ti"
  },
  { 
    img: img3, 
    name: "Restauración",
    description: "Devuelve la vida a tus prendas antiguas"
  },
  { 
    img: img4, 
    name: "Confección",
    description: "Creamos tus diseños desde cero con máxima calidad"
  }
];
</script>

<style scoped>
@import url("https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css");

#cards {
  max-width: 1400px;
  padding: 0 2rem;
  margin: 0 auto;
  min-height: 70vh;
}

.main-content {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.swiper {
  width: 100%;
  padding: 60px 20px;
}

.slide-wrapper {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.slide-image {
  width: 100%;
  height: 100%;
  border-radius: 20px;
  object-fit: cover;
  display: block;
  cursor: pointer;
  transition: all 0.4s ease;
}

.swiper-slide {
  width: 300px;
  height: 350px;
}

.swiper-slide-active .slide-image {
  border-radius: 24px;
  box-shadow: 0 25px 50px rgba(108, 26, 139, 0.25);
  filter: brightness(1.05);
}

/* Flechas mejoradas con gradiente */
.prevArrowBtn,
.nextArrowBtn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 3.2rem;
  height: 3.2rem;
  border-radius: 50%;
  background: linear-gradient(135deg, #6c1a8b 0%, #ec4899 100%);
  color: white;
  display: grid;
  place-items: center;
  font-size: 1.4rem;
  cursor: pointer;
  box-shadow: 0 4px 20px rgba(108, 26, 139, 0.2);
  transition: all 0.3s ease;
  z-index: 10;
  border: 2px solid transparent;
}

.prevArrowBtn:hover,
.nextArrowBtn:hover {
  transform: translateY(-50%) scale(1.2);
  box-shadow: 0 8px 30px rgba(108, 26, 139, 0.4);
  background: linear-gradient(135deg, #ec4899 0%, #6c1a8b 100%);
}

.prevArrowBtn {
  left: 20px;
}

.nextArrowBtn {
  right: 20px;
}

.swiper-pagination {
  margin-top: 40px;
  padding-bottom: 10px;
  display: flex;
  justify-content: center;
}

.swiper-pagination-bullet {
  background: linear-gradient(135deg, #d4d4d4, #e5e7eb);
  height: 12px;
  width: 12px;
  opacity: 1;
  border-radius: 100%;
  transition: all 0.3s ease;
  margin: 0 6px;
  cursor: pointer;
}

.swiper-pagination-bullet:hover {
  background: linear-gradient(135deg, #9ca3af, #6b7280);
  transform: scale(1.2);
}

.swiper-pagination-bullet-active {
  width: 32px;
  border-radius: 6px;
  background: linear-gradient(135deg, #6c1a8b 0%, #ec4899 100%);
  box-shadow: 0 4px 15px rgba(108, 26, 139, 0.3);
}

/* Responsive */
@media (max-width: 768px) {
  #cards {
    padding: 0 1rem;
  }

  .swiper-slide {
    width: 250px;
    height: 300px;
  }

  .prevArrowBtn,
  .nextArrowBtn {
    width: 2.8rem;
    height: 2.8rem;
    font-size: 1.2rem;
  }
}

@media (max-width: 576px) {
  .swiper-slide {
    width: 200px;
    height: 250px;
  }

  .prevArrowBtn {
    left: 10px;
  }

  .nextArrowBtn {
    right: 10px;
  }

  .swiper {
    padding: 40px 10px;
  }
}
</style>