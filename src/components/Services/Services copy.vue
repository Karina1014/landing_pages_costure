<template>
  <section id="cards">
    <h2>Our Team</h2>

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
            <img :src="item.img" />
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

// === Importa tus imágenes ===
import img1 from "@/assets/home/costura1.png";
import img2 from "@/assets/home/costura2.png";
import img3 from "@/assets/home/costura3.png";
import img4 from "@/assets/home/costura4.png";

// === Lista ===
const slides = [
  { img: img1, name: "Rohit Sharma", role: "Top Order Batter" },
  { img: img2, name: "Virat Kohli", role: "Top Order Batter" },
  { img: img3, name: "Jasprit Bumrah", role: "Bowler" },
  { img: img4, name: "Hardik Pandya", role: "All Rounder" }
];
</script>

<style scoped>

h2 {
  font-size: 2.5rem;
  color: #fff;
  font-weight: 600;
  text-align: center;
  padding-bottom: 30px;
}

h4 {
  font-size: 1.25rem;
  color: #fff;
  font-weight: 600;
}

p {
  color: #fff;
}

#cards {
  max-width: 1070px;
  padding: 0 2rem;
  margin: 2rem auto;
  min-height: 70vh;
}

.main-content {
  position: relative;
}

.card-content {
  background-color: rgba(249, 249, 249, 0.06);
  cursor: pointer;
  text-align: center;
  padding: 3rem 0;
  border-radius: 12px;
  transition: 0.3s ease-in-out;
}

.card-content:hover {
  transform: scale(1.03);
}

.card-content img {
  border-radius: 50%;
  width: 160px;
  height: 160px;
  border: 5px solid white;
  object-fit: cover;
}

.card-title {
  padding-top: 2rem;
}

/* Flechas */
.prevArrowBtn,
.nextArrowBtn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 2.9rem;
  height: 2.9rem;
  border-radius: 50%;
  border: 1px solid #fff;
  color: white;
  display: grid;
  place-items: center;
  font-size: 1.4rem;
  cursor: pointer;
  opacity: 0;
  transition: 0.4s ease;
}

.main-content:hover .prevArrowBtn,
.main-content:hover .nextArrowBtn {
  opacity: 1;
}

.prevArrowBtn {
  left: -20px;
}
.nextArrowBtn {
  right: -20px;
}

.swiper-pagination {
  margin-top: 20px;
}

.swiper-pagination-bullet {
  background-color: #ffffff;
  height: 10px;
  width: 10px;
  opacity: 1;
  border-radius: 100%;
}

.swiper-pagination-bullet-active {
  width: 22px;
  border-radius: 7px;
  background-color: #ea534a;
}
</style>
