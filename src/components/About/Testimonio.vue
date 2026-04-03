<template>
  <section id="testimonios" class="w-full bg-white py-16 lg:py-24 overflow-hidden relative">
    
    <!-- Título y Encabezado -->
    <div class="max-w-7xl mx-auto px-6 lg:px-12 mb-12 text-center">
      <div class="flex flex-col items-center gap-3">
        <span class="text-[9px] font-black uppercase tracking-[0.4em] text-[#831378] opacity-60">Experiencias Reales</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-black text-gray-900 leading-tight tracking-tighter">
          Voces de <span class="text-[#831378]">Confianza</span>
        </h2>
      </div>
    </div>

    <!-- Grid de testimonios (Compacto) -->
    <div class="max-w-6xl mx-auto px-6">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 lg:gap-8">
        <div
          v-for="(item, i) in testimonios"
          :key="i"
          class="bg-[#FAF9FC] rounded-[2rem] p-8 flex flex-col items-center text-center border border-gray-100/50 shadow-sm transition-all duration-500 hover:shadow-xl hover:-translate-y-1"
        >
          <div class="relative mb-6">
            <img
              :src="item.avatar"
              :alt="item.nombre"
              class="w-16 h-16 rounded-full object-cover grayscale hover:grayscale-0 transition-all duration-500 border-2 border-white shadow-md"
            />
            <div class="absolute -bottom-1 -right-1 bg-[#831378] w-5 h-5 rounded-full flex items-center justify-center border-2 border-white">
              <Quote class="text-white w-2.5 h-2.5 fill-current" />
            </div>
          </div>
          
          <p class="text-gray-600 mb-6 italic-style text-[0.95rem] leading-relaxed">
            "{{ item.mensaje }}"
          </p>
          
          <div class="mt-auto">
            <h3 class="text-gray-900 font-black text-sm uppercase tracking-wider mb-1">{{ item.nombre }}</h3>
            <span class="text-[#831378]/60 text-[10px] font-bold uppercase tracking-[0.2em]">{{ item.empresa }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Quote } from 'lucide-vue-next';
import avatar1 from "@/assets/home/persona1.png";
import avatar2 from "@/assets/home/persona3.png";
import avatar3 from "@/assets/home/persona2.png";

const testimonios = [
  {
    nombre: "Ana Martínez",
    empresa: "Diseños Creativos",
    mensaje: "Excelente servicio y atención personalizada. La precisión en los ajustes es realmente de otro nivel.",
    avatar: avatar1,
  },
  {
    nombre: "Carlos López",
    empresa: "Moda Urbana",
    mensaje: "Mi experiencia fue increíble. Lograron rescatar prendas que daba por perdidas con una maestría única.",
    avatar: avatar2,
  },
  {
    nombre: "María Gómez",
    empresa: "Estilo y Confort",
    mensaje: "Se nota la pasión por el oficio en cada detalle. Mis prendas ahora se ajustan perfectamente a mi estilo.",
    avatar: avatar3,
  },
];
</script>

<style scoped>
.italic-style {
  font-family: serif;
  font-style: italic;
}
</style>