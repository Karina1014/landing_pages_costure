<template>
  <section id="cards">
    <h2>Servicios</h2>

    <div class="main-content">
      <Swiper
        :modules="[Navigation, Pagination]"
        :loop="true"
        :slides-per-view="1"
        :space-between="30"
        :pagination="{
          el: '.swiper-pagination',
          clickable: true
        }"
        :navigation="{
          nextEl: '.nextArrowBtn',
          prevEl: '.prevArrowBtn'
        }"
        :breakpoints="{
          576: { slidesPerView: 2 },
          768: { slidesPerView: 3 }
        }"
        class="swiper"
      >
        <SwiperSlide v-for="(item, i) in slides" :key="i">
          <div class="card-content">
            <img :src="item.img" class="service-img" />
            <div class="card-title">
              <h4>{{ item.name }}</h4>
              <p>{{ item.role }}</p>
            </div>
          </div>
        </SwiperSlide>
      </Swiper>

      <!-- Flechas -->
      <div class="prevArrowBtn">
        <i class="bx bx-chevron-left"></i>
      </div>
      <div class="nextArrowBtn">
        <i class="bx bx-chevron-right"></i>
      </div>

      <!-- Bullets -->
      <div class="swiper-pagination"></div>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Navigation } from "swiper/modules";

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

// IMPORTA TUS IMÁGENES
import img1 from "@/assets/home/costura1.png";
import img2 from "@/assets/home/costura2.png";
import img3 from "@/assets/home/costura3.png";

const slides = [
  { img: img1, name: "Servicio 1", role: "Descripción" },
  { img: img2, name: "Servicio 2", role: "Descripción" },
  { img: img3, name: "Servicio 3", role: "Descripción" }
];
</script>
<style scoped>
@import url("https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css");

/* Título */
h2 {
  font-size: 1.8rem;
  color: #222;
  font-weight: 700;
  text-align: center;
  margin-bottom: 2rem;
}

/* Contenedor principal */
#cards {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem 0;
}

/* Fondo blanco como en la imagen */
.main-content {
  background: white;
  padding: 2rem 0 3rem;
  border-radius: 20px;
  position: relative;
}

/* Card general */
.card-content {
  text-align: center;
  transition: 0.3s ease;
}

/* Imágenes cuadradas redondeadas */
.service-img {
  width: 230px;
  height: 230px;
  object-fit: cover;
  border-radius: 35px;
  transition: 0.3s ease;
}

/* EFECTO: la imagen central más grande */
.swiper-slide-active .service-img {
  transform: scale(1.18);
}

/* Slides laterales más pequeñas */
.swiper-slide .service-img {
  transform: scale(0.9);
  opacity: 0.9;
}

/* Títulos dentro de cada card */
.card-title {
  margin-top: 1rem;
}

.card-title h4 {
  color: #222;
  font-weight: 600;
}

.card-title p {
  color: #444;
  font-size: 0.9rem;
}

/* Flechas */
.prevArrowBtn,
.nextArrowBtn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: #fff;
  border: 1px solid #444;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  font-size: 1.4rem;
  color: #444;
  z-index: 10;
  transition: 0.3s;
}

.prevArrowBtn:hover,
.nextArrowBtn:hover {
  background: #eee;
}

.prevArrowBtn {
  left: 10px;
}
.nextArrowBtn {
  right: 10px;
}

/* Bullets (morado como en la imagen) */
.swiper-pagination {
  margin-top: 1.5rem;
}

.swiper-pagination-bullet {
  background-color: #7a0fc0 !important;
  opacity: 0.3;
  width: 10px;
  height: 10px;
}

.swiper-pagination-bullet-active {
  opacity: 1;
  width: 12px;
  height: 12px;
}
</style>
