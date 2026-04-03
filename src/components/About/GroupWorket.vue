<template>
  <section id="equipo" class="w-full bg-white py-16 lg:py-24 overflow-hidden relative">
    
    <!-- Título y Encabezado (Estilo Editorial) -->
    <div class="max-w-7xl mx-auto px-6 lg:px-12 mb-16 text-center lg:text-left">
      <div class="flex flex-col items-center lg:items-start gap-3">
        <span class="text-[9px] font-black uppercase tracking-[0.4em] text-[#831378] opacity-60">Maestría Humana</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-black text-gray-900 leading-tight tracking-tighter">
          Nuestro <span class="text-[#831378]">Equipo</span>
        </h2>
        <div class="h-[1px] w-12 bg-[#831378]/30 mt-1"></div>
      </div>
    </div>

    <!-- Layout de Galería Editorial Asimétrica -->
    <div class="max-w-7xl mx-auto px-6 lg:px-12">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-stretch">
        
        <!-- CARD PRINCIPAL: El Corazón del Taller (Lado Izquierdo) -->
        <div class="lg:col-span-7 group relative">
          <div class="absolute -inset-2 bg-gradient-to-tr from-[#831378]/10 to-transparent rounded-[3rem] blur-2xl opacity-0 group-hover:opacity-100 transition duration-700"></div>
          <div class="relative h-[400px] lg:h-[600px] rounded-[2.5rem] overflow-hidden shadow-2xl border border-gray-100 bg-gray-50">
            <img 
              :src="teamMain" 
              alt="Colaboración en el atelier" 
              class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-1000"
            />
            <!-- Info Overlay -->
            <div class="absolute bottom-0 left-0 right-0 p-8 lg:p-12 bg-gradient-to-t from-black/80 via-black/20 to-transparent text-white translate-y-4 opacity-0 group-hover:translate-y-0 group-hover:opacity-100 transition-all duration-500">
              <h3 class="text-2xl font-black tracking-tight">Colaboración Creativa</h3>
              <p class="text-sm opacity-80 mt-2 font-medium italic-style">Donde cada visión se perfecciona en conjunto.</p>
            </div>
          </div>
        </div>

        <!-- COLUMNA DERECHA: Detalles de Maestría -->
        <div class="lg:col-span-5 flex flex-col gap-8">
          
          <!-- Card de Detalle 1: Precisión -->
          <div class="flex-1 group relative">
             <div class="relative h-[250px] lg:h-full rounded-[2.5rem] overflow-hidden shadow-xl border border-gray-100 bg-gray-50">
                <img 
                  :src="teamDetail1" 
                  alt="Maestro sastre trazando" 
                  class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-1000"
                />
                <div class="absolute inset-0 bg-white/10 group-hover:bg-transparent transition-colors"></div>
                <div class="absolute top-6 left-6">
                  <span class="px-4 py-2 bg-white/90 backdrop-blur-md rounded-full text-[9px] font-black uppercase tracking-widest text-gray-900 shadow-sm">
                    Precisión Técnica
                  </span>
                </div>
             </div>
          </div>

          <!-- Card de Detalle 2: Pasión -->
          <div class="flex-1 group relative">
             <div class="relative h-[250px] lg:h-full rounded-[2.5rem] overflow-hidden shadow-xl border border-gray-100 bg-gray-50">
                <img 
                  :src="teamDetail2" 
                  alt="Retrato de experta costurera" 
                  class="w-full h-full object-cover transform group-hover:rotate-2 group-hover:scale-110 transition-transform duration-1000"
                />
                <div class="absolute inset-0 bg-[#831378]/5 group-hover:bg-transparent transition-colors"></div>
                <div class="absolute bottom-6 right-6 text-right">
                  <p class="text-white font-black text-xs uppercase tracking-widest drop-shadow-lg">Pasión por el detalle</p>
                </div>
             </div>
          </div>

        </div>

      </div>

      <!-- Texto Inferior / Misión (Estilo Minimalista) -->
      <div class="mt-20 max-w-2xl mx-auto text-center space-y-6">
        <p class="text-gray-400 text-[10px] font-black uppercase tracking-[0.5em]">El Alma del Atelier</p>
        <p class="text-xl sm:text-2xl text-gray-800 leading-relaxed font-bold italic-style px-4">
          "No solo ajustamos prendas, esculpimos confianza a través de manos expertas y corazones dedicados a la perfección."
        </p>
        <div class="h-[2px] w-8 bg-[#831378]/20 mx-auto mt-4"></div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Import de imágenes generadas
const teamMain = new URL('./../../atelier_team_working_1775252740946.png', import.meta.url).href
const teamDetail1 = new URL('./../../tailor_hand_drafting_1775252755385.png', import.meta.url).href
const teamDetail2 = new URL('./../../professional_seamstress_portrait_1775252769946.png', import.meta.url).href
</script>

<style scoped>
.italic-style {
  font-family: serif;
  font-style: italic;
}

section {
  animation: fadeIn 1.5s cubic-bezier(0.23, 1, 0.32, 1) forwards;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>