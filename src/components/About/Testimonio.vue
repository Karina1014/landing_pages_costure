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

    <!-- Grid de testimonios -->
    <div class="max-w-6xl mx-auto">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="(item, i) in testimonios"
          :key="i"
          class="bg-white rounded-2xl shadow-lg p-8 flex flex-col items-center text-center transition-transform duration-300 hover:scale-105 hover:shadow-xl"
        >
          <img
            :src="item.avatar"
            :alt="item.nombre"
            class="w-20 h-20 rounded-full mb-4 object-cover"
          />
          <p class="text-gray-700 mb-4 italic">"{{ item.mensaje }}"</p>
          <h3 class="text-[#831378] font-bold">{{ item.nombre }}</h3>
          <span class="text-gray-500 text-sm">{{ item.empresa }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
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
/* Animación suave al cargar */
@media (prefers-reduced-motion: no-preference) {
  div {
    animation: fadeInUp 0.6s ease-out;
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>