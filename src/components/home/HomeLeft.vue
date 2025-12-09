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
  <div :class="{'fade-in-up': isLoaded}" class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 pt-24">
    <!-- Etiqueta de ubicación -->
    <h3 class="inline-block bg-[#C991DB] py-1 px-2 rounded text-sky-900 text-xs font-medium tracking-normal shadow-sm">
      Costura en Quito, Carolina
    </h3>

    <!-- Título principal -->
    <h2 :class="{'fade-in-up': isLoaded}" class="text-left text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-extrabold leading-tight max-w-3xl tracking-tight mt-3">
      <span class="text-black">Tu </span>
      <span class="text-[#80196D] ml-1">vestuario </span>
      <span class="text-black">en</span>
      <br />
      <span class="text-[#80196D] ml-1">Manos Expertas</span>
    </h2>

    <!-- Descripción -->
    <p :class="{'fade-in-up': isLoaded}" class="text-left  text-black text-base md:text-lg lg:text-xl max-w-3xl leading-snug tracking-wide mt-3 mb-4">
      Nos dedicamos a que tu ropa te haga sentir increíble, especializada en un estilo que realmente te representa
    </p>

    <!-- Indicador de personas -->
    <div :class="{'fade-in-up': isLoaded}" class="mt-4 inline-flex items-center rounded-[20px] bg-[#831378] px-2 py-1">
      <div class="inline-flex relative rounded-full overflow-hidden space-x-[-10px] h-8">
        <img :src="veterinariaImg1" alt="Mascota 1" class="w-8 h-8 rounded-full object-cover z-10" />
        <img :src="veterinariaImg2" alt="Mascota 2" class="w-8 h-8 rounded-full object-cover z-20" />
        <img :src="veterinariaImg3" alt="Mascota 3" class="w-8 h-8 rounded-full object-cover z-30" />
      </div>
      <span class="ml-2 text-white font-semibold text-xs sm:text-sm md:text-base">+100 Clientes atendidos</span>
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
