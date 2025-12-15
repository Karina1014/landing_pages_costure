<template>
  <section class="w-full bg-gradient-to-br from-white via-purple-50 to-white py-20">
    <div class="max-w-7xl mx-auto px-6">
      <!-- Título general -->
      <div class="text-center mb-16">
        <h2 class="text-4xl sm:text-5xl font-bold mb-3">
          Nos encontramos en
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-[#831378] to-purple-900">
            Carolina
          </span>
        </h2>
        <p class="text-gray-600 text-lg max-w-2xl mx-auto">
          Visita nuestro atelier y descubre la magia de la alta costura
        </p>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- MAPA -->
        <div class="relative group">
          <div class="absolute -inset-1 bg-gradient-to-r from-[#831378] to-purple-600 rounded-3xl blur opacity-25 group-hover:opacity-100 transition duration-500"></div>
          
          <div class="relative rounded-3xl overflow-hidden shadow-2xl bg-white">
            <iframe
              class="w-full h-96"
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15959.18896030821!2d-78.49531726289587!3d-0.1862512969906275!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x91d59a7ce9ba8755%3A0x755f2bd0d36e70a7!2sLa%20Carolina%2C%20Quito%2C%20Ecuador!5e0!3m2!1ses-419!2sus!4v1765773002577!5m2!1ses-419!2sus"
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              title="Ubicación en Google Maps"
            ></iframe>
          </div>

          <!-- Badge de ubicación
          <div class="absolute -bottom-4 -right-4 bg-[#831378] text-white px-4 py-2 rounded-full shadow-lg font-semibold text-sm">
            📍 Latacunga
          </div> -->
        </div>

        <!-- CONTENIDO -->
        <div class="space-y-8">
          <!-- Descripción principal -->
          <div>
            <h3 class="text-3xl font-bold text-gray-900 mb-4">
              Arreglos de Alta Costura
            </h3>
            <p class="text-gray-700 text-lg leading-relaxed mb-6">
              Presentamos nuestro servicio de <span class="font-semibold text-[#831378]">arreglos de alta costura</span> basado en la experiencia y la pasión por cada detalle.
            </p>
            <p class="text-gray-700 text-lg leading-relaxed">
              Transformamos y adaptamos sin esfuerzo cada prenda para que se ajuste perfectamente a tu cuerpo y estilo. Tu confianza es nuestra prioridad.
            </p>
          </div>

          <!-- Información de contacto -->
          <div class="space-y-4 pt-4 border-t-2 border-purple-200">
            <div class="flex items-center gap-4">
              <div class="w-12 h-12 bg-gradient-to-br from-[#831378] to-purple-600 rounded-full flex items-center justify-center text-white text-xl">
                📍
              </div>
              <div>
                <p class="font-semibold text-gray-900">Ubicación</p>
                <p class="text-gray-600">Latacunga, Pichincha - Ecuador</p>
              </div>
            </div>

            <div class="flex items-center gap-4">
              <div class="w-12 h-12 bg-gradient-to-br from-[#831378] to-purple-600 rounded-full flex items-center justify-center text-white text-xl">
                📱
              </div>
              <div>
                <p class="font-semibold text-gray-900">Teléfono</p>
                <a href="tel:+593" class="text-[#831378] hover:text-purple-600 transition">
                  Llamar ahora
                </a>
              </div>
            </div>

            <div class="flex items-center gap-4">
              <div class="w-12 h-12 bg-gradient-to-br from-[#831378] to-purple-600 rounded-full flex items-center justify-center text-white text-xl">
                🕐
              </div>
              <div>
                <p class="font-semibold text-gray-900">Horario</p>
                <p class="text-gray-600">Lunes a Viernes: 9 AM - 6 PM</p>
              </div>
            </div>
          </div>

          <!-- Botón de contacto mejorado -->
          <div class="flex flex-col sm:flex-row gap-4 pt-4">
            <button
              class="px-8 py-4 bg-gradient-to-r from-[#831378] to-purple-600 hover:from-purple-700 hover:to-purple-800 text-white font-bold rounded-full transition duration-300 shadow-lg hover:shadow-xl transform hover:scale-105"
            >
              Contáctanos
            </button>
            <button
              class="px-8 py-4 border-2 border-[#831378] text-[#831378] hover:bg-purple-50 font-bold rounded-full transition duration-300"
            >
              Más Información
            </button>
          </div>
        </div>
      </div>

    
    </div>
  </section>
</template>

<script setup>
// Lógica de contacto aquí si es necesario
</script>

<style scoped>
/* Animación suave */
@media (prefers-reduced-motion: no-preference) {
  section {
    animation: fadeIn 0.8s ease-out;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>