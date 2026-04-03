<template>
  <section id="sobreNosotros" class="w-full bg-[#FAF9FC] py-20 lg:py-32 overflow-hidden relative">
    <!-- Decoración de fondo: Marca de agua sutil -->
    <div class="absolute top-10 right-[-5%] text-[15rem] font-black text-gray-100/50 select-none pointer-events-none italic-style leading-none">
      Entre Hilos & Agujas  
    </div>

    <div class="max-w-7xl mx-auto px-6 lg:px-12 relative z-10">
      <div class="flex flex-col lg:flex-row items-center gap-20 lg:gap-32">
        
        <!-- ======== CONTENIDO TEXTUAL (Primero en móvil) ======== -->
        <div class="w-full lg:flex-1 flex flex-col items-start gap-8 order-1">
          
          <div class="space-y-4">
            <div class="flex items-center gap-4">
              <span class="text-[11px] font-black uppercase tracking-[0.5em] text-[#831378]">Quiénes Somos</span>
              <div class="h-[1px] flex-1 bg-gradient-to-r from-[#831378]/30 to-transparent"></div>
            </div>

            <h2 class="text-4xl sm:text-5xl font-bold text-gray-900 leading-[0.95] tracking-tighter">
              La Magia del <br />
              <span class="text-[#831378] drop-shadow-sm">Ajuste Perfecto</span>
            </h2>
          </div>

          <p class="text-xl text-gray-600 leading-relaxed max-w-lg font-medium">
            Presentamos nuestro servicio de <span class="text-gray-900 font-bold border-b-2 border-[#831378]/20">Arreglos de Alta Costura</span> basado en la experiencia y la precisión de cada detalle.
          </p>

          <div class="relative bg-white/50 backdrop-blur-sm p-8 rounded-3xl border border-[#831378]/5 group-hover:border-[#831378]/10 transition-colors">
            <div class="absolute -top-3 -left-3 text-4xl text-[#831378]/20 italic-style font-black">"</div>
            <p class="text-gray-700 italic-style text-xl leading-relaxed relative z-10">
              Transformamos y adaptamos <span class="text-[#831378] font-bold">sin esfuerzo</span> cada prenda para que se ajuste <span class="text-[#831378] font-bold">perfectamente</span> a tu cuerpo y estilo personal.
            </p>
          </div>
        </div>

        <!-- ======== IMAGEN CREATIVA (Después en móvil) ======== -->
        <div class="w-full lg:w-[38%] relative group px-4 order-2">
          <!-- Decoración: Círculo de fondo animado -->
          <div class="absolute -top-10 -left-10 w-48 h-48 bg-[#831378]/5 rounded-full blur-[80px] group-hover:bg-[#831378]/10 transition-all duration-1000"></div>
          
          <div class="relative">
            <!-- Capa 1: Borde de Costura (Stitches) -->
            <div class="absolute inset-0 border-2 border-dashed border-[#831378]/20 rounded-[2.5rem] rotate-3 group-hover:rotate-0 "></div>
            
            <!-- Capa 2: Contenedor Imagen -->
            <div class="relative aspect-[4/5] rounded-[2rem] overflow-hidden shadow-[0_40px_80px_-15px_rgba(0,0,0,0.2)] bg-white z-10 transform -rotate-2 ">
              <img
                :src="costuraImg"
                alt="Creatividad en Costura"
                class="w-full h-full object-cover transition-transform  "
              />
              
              <!-- Efecto Lente/Brillo -->
              <div class="absolute inset-0 bg-gradient-to-tr from-[#831378]/20 via-transparent to-white/10 mix-blend-overlay"></div>
              
              <!-- Badge Flotante (Refinado) -->
              <div class="absolute bottom-6 left-6 right-6 bg-black/40 backdrop-blur-md border border-white/10 p-4 rounded-xl transform translate-y-2 opacity-0 group-hover:translate-y-0 group-hover:opacity-100 transition-all duration-500 text-center">
                <p class="text-white font-bold text-sm tracking-tight italic-style">Arte en cada puntada</p>
              </div>
            </div>

            <!-- Adorno: Icono de Tijeras -->
            <div class="absolute -bottom-4 -right-4 w-16 h-16 bg-white rounded-full shadow-xl flex items-center justify-center z-20 border border-gray-100 animate-bounce-slow">
              <div class="w-10 h-10 rounded-full border border-dashed border-[#831378]/30 flex items-center justify-center">
                <Scissors class="w-5 h-5 text-[#831378] transform -rotate-45" />
              </div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { ArrowRight, Scissors } from 'lucide-vue-next'
const costuraImg = new URL('@/assets/logo/About.jpeg', import.meta.url).href
</script>

<style scoped>
@keyframes reveal-up {
  0% {
    opacity: 0;
    transform: translateY(40px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounce-slow {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

/* .animate-bounce-slow {
  animation: bounce-slow 4s ease-in-out infinite;
} */

section {
  animation: reveal-up 1.2s cubic-bezier(0.23, 1, 0.32, 1) forwards;
}

.italic-style {
  font-family: serif;
  font-style: italic;
  font-weight: 500;
}
</style>