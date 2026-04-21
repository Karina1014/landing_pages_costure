<template>
  <section id="visita" class="w-full bg-white py-12 lg:py-16 overflow-hidden relative">
    
    <!-- Título y Encabezado (Estilo Editorial) -->
    <div class="max-w-7xl mx-auto px-6 lg:px-12 mb-12 text-center lg:text-left">
      <div class="flex flex-col items-center lg:items-start gap-3">
        <span class="text-[9px] font-black uppercase tracking-[0.4em] text-[#831378] opacity-60">Atelier Principal</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-black text-gray-900 leading-tight tracking-tighter">
          Nuestra <span class="text-[#831378]">Ubicación</span>
        </h2>
      </div>
    </div>

    <!-- Contenedor Mapa e Info -->
    <div class="max-w-7xl mx-auto px-6 lg:px-12">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
        
        <!-- MAPA (Lado Izquierdo - Gran Formato) -->
        <div class="lg:col-span-7 relative group">
          <div class="absolute -inset-2 bg-[#831378]/5 rounded-[3rem] blur-xl opacity-50 group-hover:opacity-100 transition duration-700"></div>
          <div class="relative rounded-[2.5rem] overflow-hidden shadow-2xl border border-gray-100 bg-white aspect-video lg:aspect-auto lg:h-[450px]">
            <iframe
              class="w-full h-full grayscale hover:grayscale-0 transition-all duration-1000"
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15959.18896030821!2d-78.49531726289587!3d-0.1862512969906275!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x91d59a7ce9ba8755%3A0x755f2bd0d36e70a7!2sLa%20Carolina%2C%20Quito%2C%20Ecuador!5e0!3m2!1ses-419!2sus!4v1765773002577!5m2!1ses-419!2sus"
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              title="Ubicación en Google Maps"
            ></iframe>
          </div>
        </div>

        <!-- INFO Y CONTACTO (Lado Derecho) -->
        <div class="lg:col-span-5 space-y-10">
          
          <div class="space-y-4">
            <h3 class="text-2xl font-black text-gray-900 tracking-tight">Estamos cerca de ti</h3>
            <p class="text-gray-600 leading-relaxed font-medium italic-style">
              Un espacio dedicado a la precisión y el estilo personal. Agenda tu cita para una experiencia totalmente personalizada.
            </p>
          </div>

          <!-- Items de Contacto (Minimalista) -->
          <div class="space-y-6">
            <div class="flex items-start gap-4 group">
              <div class="w-10 h-10 rounded-xl bg-[#831378]/5 flex items-center justify-center text-[#831378] group-hover:bg-[#831378] group-hover:text-white transition-all duration-300">
                <MapPin class="w-5 h-5" />
              </div>
              <div>
                <p class="text-[10px] font-black uppercase tracking-widest text-[#831378]/40 mb-1">Dirección</p>
                <p class="text-gray-700 font-bold text-sm">Latacunga, Pichincha - Ecuador</p>
              </div>
            </div>

            <div class="flex items-start gap-4 group">
              <div class="w-10 h-10 rounded-xl bg-[#831378]/5 flex items-center justify-center text-[#831378] group-hover:bg-[#831378] group-hover:text-white transition-all duration-300">
                <Phone class="w-5 h-5" />
              </div>
              <div>
                <p class="text-[10px] font-black uppercase tracking-widest text-[#831378]/40 mb-1">Teléfono</p>
                <a href="tel:+593" class="text-gray-700 font-bold text-sm hover:text-[#831378] transition-colors">
                  Contactar vía Llamada
                </a>
              </div>
            </div>

            <div class="flex items-start gap-4 group">
              <div class="w-10 h-10 rounded-xl bg-[#831378]/5 flex items-center justify-center text-[#831378] group-hover:bg-[#831378] group-hover:text-white transition-all duration-300">
                <Clock class="w-5 h-5" />
              </div>
              <div>
                <p class="text-[10px] font-black uppercase tracking-widest text-[#831378]/40 mb-1">Atención</p>
                <p class="text-gray-700 font-bold text-sm">Lun - Vie: 9 AM a 6 PM</p>
              </div>
            </div>
          </div>

          <!-- CTAs (Compacto) -->
          <div class="flex flex-wrap gap-4 pt-4">
            <button class="px-8 py-4 bg-gray-900 text-white rounded-2xl font-black text-[10px] uppercase tracking-[0.2em] hover:bg-[#831378] transition-all duration-300 shadow-xl shadow-gray-200">
              Agendar Cita
            </button>
            <button class="px-8 py-4 border border-gray-200 text-gray-900 rounded-2xl font-black text-[10px] uppercase tracking-[0.2em] hover:bg-gray-50 transition-all duration-300">
              Ver Catálogo
            </button>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { MapPin, Phone, Clock } from 'lucide-vue-next';
</script>

<style scoped>
.italic-style {
  font-family: serif;
  font-style: italic;
}
</style>