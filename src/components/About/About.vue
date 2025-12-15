<template>
  <section id="sobreNosotros" class="w-full bg-gradient-to-br from-[#eaeaea] via-white to-[#f5f5f5] py-8 sm:py-12 md:py-16 lg:py-20">

    <!-- CONTENEDOR PRINCIPAL -->
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col lg:flex-row items-center gap-8 sm:gap-10 md:gap-12 lg:gap-16">

      <!-- ======== IMAGEN TIPO REEL ======== -->
      <div class="w-full lg:w-1/2 flex justify-center order-2 lg:order-1 px-2 sm:px-0">
        <div class="relative w-full max-w-[320px] sm:max-w-[340px] md:max-w-[380px] aspect-[9/14] bg-white shadow-2xl rounded-[30px] sm:rounded-[35px] overflow-hidden flex items-center justify-center group">
          <img
            :src="costuraImg"
            alt="Trabajo de costura"
            class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
          />

          <!-- EFECTO SUPERIOR -->
          <div class="absolute top-0 left-0 w-full h-20 sm:h-24 bg-gradient-to-b from-black/40 to-transparent"></div>

          <!-- EFECTO INFERIOR -->
          <div class="absolute bottom-0 left-0 w-full h-24 sm:h-28 bg-gradient-to-t from-black/50 to-transparent"></div>

          <!-- TEXTO ESTILO REEL -->
          <div class="absolute bottom-4 sm:bottom-6 left-4 sm:left-6 text-white">
            <p class="text-base sm:text-lg font-semibold">Costura & Diseño</p>
            <p class="text-xs sm:text-sm opacity-90">@costura_experta</p>
          </div>
        </div>
      </div>

      <!-- ======== TEXTO MEJORADO ======== -->
      <div class="w-full lg:w-1/2 flex flex-col gap-4 sm:gap-5 md:gap-6 order-1 lg:order-2 px-2 sm:px-0">
        
        <!-- HEADER CON DECORACIÓN -->
        <div class="space-y-2 sm:space-y-3">
          <div class="flex items-center gap-2 sm:gap-3 mb-2 sm:mb-3">
            <div class="h-1 w-8 sm:w-12 bg-gradient-to-r from-[#831378] rounded-full"></div>
            <span class="text-xs sm:text-sm font-semibold text-[#831378] uppercase tracking-widest">
              Quiénes Somos
            </span>
          </div>
          
          <h2 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold leading-tight">
            <span class="text-black">🧵 La Magia del </span>
            <br class="hidden sm:block" />
              Ajuste Perfecto
            
          </h2>
        </div>

        <!-- PÁRRAFO CON MEJOR TIPOGRAFÍA -->
        <p class="text-base sm:text-lg md:text-lg lg:text-xl text-gray-600 leading-relaxed font-light">
          Presentamos nuestro servicio de <span class="font-semibold text-[#831378]">Arreglos de Alta Costura</span> basado en la experiencia y la precisión de cada detalle.
        </p>

     

        <!-- TEXTO FINAL CON ÉNFASIS -->
        <div class="bg-gradient-to-r from-[#6c1a8b]/5 border-l-4 border-[#831378] p-4 sm:p-5 md:p-6 rounded-lg mt-2 sm:mt-4">
          <p class="text-sm sm:text-base md:text-lg text-gray-700 leading-relaxed">
            Transformamos y adaptamos <span class="font-bold text-[#831378]">sin esfuerzo</span> cada prenda para que se ajuste <span class="font-bold text-[#831378]">perfectamente</span> a tu cuerpo y estilo personal.
          </p>
        </div>

      <!-- CTA BUTTON - RESPONSIVE -->
    <div class="flex justify-center lg:justify-start mt-4 sm:mt-6 md:mt-8">
      <button
        class="
          group
          inline-flex items-center gap-2
          px-6 sm:px-8
          py-2.5 sm:py-3
          bg-[#831378]
          text-white font-bold text-sm sm:text-base
          rounded-full
          transition-all duration-300
          hover:scale-105
          hover:shadow-xl
          active:scale-95
          w-full sm:w-auto
          justify-center sm:justify-start
        "
      >
        Conoce Nuestros Servicios
        <svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6" />
        </svg>
      </button>
    </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const costuraImg = new URL('@/assets/logo/About.jpeg', import.meta.url).href
</script>

<style scoped>
/* Animación suave de entrada */
@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

section {
  animation: slideInUp 0.8s ease-out;
}

/* Media queries adicionales para optimizar */
@media (max-width: 640px) {
  /* Ajustes extra para móviles pequeños */
  :deep(.swiper) {
    padding: 30px 10px;
  }
}

@media (max-width: 480px) {
  /* Ajustes para móviles muy pequeños */
  section {
    padding: 20px 0;
  }
}

/* Para tablets horizontales */
@media (min-width: 768px) and (max-height: 600px) {
  section {
    padding: 40px 0;
  }
}
</style>