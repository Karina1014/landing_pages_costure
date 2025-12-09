<template>
  <section id="sobreNosotros" class="w-full bg-[#eaeaea] py-10 sm:py-16">

    <!-- CONTENEDOR PRINCIPAL -->
    <div class="max-w-6xl mx-auto px-6 flex flex-col sm:flex-row items-center gap-10">

      <!-- ======== IMAGEN TIPO REEL ======== -->
      <div class="w-full sm:w-1/2 flex justify-center">
        <div class="relative w-[320px] sm:w-[380px] h-[580px] bg-white shadow-xl rounded-[35px] overflow-hidden flex items-center justify-center">
          <img
            :src="costuraImg"
            alt="Trabajo de costura"
            class="w-full h-full object-cover"
          />

          <!-- EFECTO SUPERIOR -->
          <div class="absolute top-0 left-0 w-full h-24 bg-gradient-to-b from-black/40 to-transparent"></div>

          <!-- EFECTO INFERIOR -->
          <div class="absolute bottom-0 left-0 w-full h-28 bg-gradient-to-t from-black/50 to-transparent"></div>

          <!-- TEXTO ESTILO REEL -->
          <div class="absolute bottom-6 left-6 text-white">
            <p class="text-lg font-semibold">Costura & Diseño</p>
            <p class="text-sm opacity-90">@costura_experta</p>
          </div>
        </div>
      </div>

    <!-- ======== TEXTO ======== -->
<div class="w-full sm:w-1/2 text-center px-4">
  <h2 class="text-3xl sm:text-4xl font-bold leading-tight mb-4 text-center">
    🧵 Sobre Nosotros <br />
    <span class="text-[#6c1a8b]">La Magia del Ajuste Perfecto</span>
  </h2>

  <p class="text-lg text-gray-700 text-center">
    Presentamos nuestro servicio de Arreglos de Alta Costura basado
    en la experiencia y la precisión. <br /><br />
    Transformamos y adaptamos sin esfuerzo cada prenda para que se ajuste
    perfectamente a tu cuerpo y estilo.
  </p>
</div>


    </div>

  </section>
</template>

<script setup>
const costuraImg = new URL('@/assets/home/costura1.png', import.meta.url).href
</script>

<style scoped>
/* Puedes agregar más estilos si necesitas */
</style>
