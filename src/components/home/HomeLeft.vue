<script setup>
import { onMounted, ref } from 'vue';
import veterinariaImg1 from '../../assets/home/persona1.png'
import veterinariaImg2 from '../../assets/home/persona3.png'
import veterinariaImg3 from '../../assets/home/persona2.png'

const isLoaded = ref(false);

onMounted(() => {
  // Cambiar el estado de isLoaded a true para activar la animación
  isLoaded.value = true;
});
</script>

<template>
  <div :class="{'fade-in-up': isLoaded}" class="w-full max-w-xl mx-auto lg:mx-0 px-4 pt-10 lg:pt-0">
    <!-- Etiqueta de ubicación -->
    <span class="inline-block bg-[#E8D5EB] text-[#831378] py-1 px-3 rounded-md text-sm font-bold tracking-tight mb-4 shadow-sm">
      Costura en Quito, Carolina
    </span>

    <!-- Título principal -->
    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-black leading-[1.1] text-gray-900 tracking-tighter mb-6">
      Tu <span class="text-[#831378]">vestuario</span> en<br />
      <span class="text-[#831378]">Manos Expertas</span>
    </h1>

    <!-- Descripción -->
    <p class="text-gray-700 text-lg sm:text-xl leading-relaxed mb-8 max-w-lg">
      Nos dedicamos a que tu ropa te haga sentir <span class="font-bold">increíble</span>, especializada en un estilo que realmente <span class="font-bold">te representa.</span>
    </p>

    <!-- Indicador de personas -->
    <div class="inline-flex items-center gap-4 bg-[#831378] pl-2 pr-8 py-2.5 rounded-xl shadow-xl shadow-[#831378]/20 transition-all hover:scale-105 hover:-translate-y-1 cursor-pointer">
      <div class="flex -space-x-2">
        <img :src="veterinariaImg1" alt="Cliente 1" class="w-10 h-10 rounded-full border-2 border-white object-cover shadow-sm" />
        <img :src="veterinariaImg2" alt="Cliente 2" class="w-10 h-10 rounded-full border-2 border-white object-cover shadow-sm" />
        <img :src="veterinariaImg3" alt="Cliente 3" class="w-10 h-10 rounded-full border-2 border-white object-cover shadow-sm" />
      </div>
      <span class="text-white font-bold text-sm sm:text-base">+ 100 Clientes atendidos</span>
    </div>
  </div>
</template>

<style scoped>
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in-up {
  animation: fadeInUp 1s ease-out;
}
</style>
