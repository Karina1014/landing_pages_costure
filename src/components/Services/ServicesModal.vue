<script setup>
import { onMounted, onUnmounted } from 'vue';
import { X, ExternalLink, Scissors, Sparkles, Wrench, Shirt, Star, Home as HomeIcon, MessageCircle, ArrowRight } from 'lucide-vue-next';
const props = defineProps({
  isOpen: Boolean,
  category: Object
});

const emit = defineEmits(['close']);

// Bloquear scroll del body cuando el modal está abierto
const handleEsc = (e) => {
  if (e.key === 'Escape') emit('close');
};

onMounted(() => window.addEventListener('keydown', handleEsc));
onUnmounted(() => window.removeEventListener('keydown', handleEsc));

const phoneNumber = '593987561663';
const message = '¡Hola Entre hilos & Agujas! Tengo una consulta sobre un arreglo. ¿Podrían Ayudarme? ✨';
const whatsappURL = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`;
</script>

<template>
  <Teleport to="body">
    <Transition name="modal-fade">
      <div v-if="isOpen" class="fixed inset-0 z-[100] flex items-center justify-center p-4 lg:p-12">
        
        <!-- Backdrop con Blur -->
        <div 
          class="absolute inset-0 bg-black/40 backdrop-blur-md transition-opacity duration-500"
          @click="emit('close')"
        ></div>

        <!-- Cuerpo del Modal (Compacto & Minimalista) -->
        <div class="relative w-full max-w-5xl h-auto max-h-[90vh] bg-white rounded-[2rem] overflow-hidden shadow-2xl flex flex-col lg:flex-row transition-all duration-500 transform border border-gray-100">
          
          <!-- Botón de Cerrar (Compacto) -->
          <button 
            @click="emit('close')" 
            class="absolute top-5 right-5 z-50 w-10 h-10 bg-white shadow-md hover:bg-gray-100 rounded-full flex items-center justify-center transition-all text-gray-400"
          >
            <X class="w-5 h-5" />
          </button>

          <!-- COLUMNA IZQUIERDA (Narrow & Pure) -->
          <div class="hidden lg:flex lg:w-[35%] relative overflow-hidden bg-gray-900">
            <img 
              :src="category.bg" 
              :alt="category.title" 
              class="absolute inset-0 w-full h-full object-cover opacity-70 group-hover:scale-105 transition-transform duration-1000" 
            />
            <div :class="category.color" class="absolute inset-0 opacity-30 mix-blend-multiply"></div>
            <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent"></div>
            
            <div class="relative z-10 p-10 flex flex-col h-full justify-end">
              <h3 class="text-4xl font-black text-white leading-none uppercase tracking-tighter mb-4 font-outfit">
                {{ category.title }}
              </h3>
              <p class="text-white/80 text-base italic font-serif leading-tight max-w-xs">
                {{ category.description }}
              </p>
            </div>
          </div>

          <!-- COLUMNA DERECHA (Lean & Readable) -->
          <div class="flex-1 overflow-y-auto bg-white p-6 lg:p-10 custom-scrollbar">
            
            <!-- Header Mobile Sync -->
            <div class="lg:hidden mb-6">
               <h3 class="text-2xl font-black text-gray-900 uppercase tracking-tighter">
                  {{ category.title }}
               </h3>
               <div class="h-1 w-8 bg-[#831378] mt-2 rounded-full"></div>
            </div>

            <div class="relative">
              <div class="flex items-center gap-3 mb-6">
                <span class="text-[9px] font-black uppercase tracking-[0.4em] text-gray-400">Servicios Disponibles</span>
                <div class="h-[1px] flex-1 bg-gray-50"></div>
              </div>
              
              <!-- Grid más compacta -->
              <div class="grid grid-cols-1 md:grid-cols-2 gap-x-8 gap-y-4">
                <div 
                  v-for="(service, idx) in category.services" 
                  :key="idx"
                  class="flex items-center gap-3 border-b border-gray-50 pb-3 hover:bg-gray-50/50 transition-all px-2 rounded-lg"
                >
                  <div class="w-1.5 h-1.5 rounded-full bg-[#831378] opacity-40"></div>
                  <p class="text-gray-700 font-bold text-sm lg:text-base tracking-tight leading-tight">
                    {{ service }}
                  </p>
                </div>
              </div>

              <!-- CTA Bottom (Magnet & Attraction) -->
              <div class="mt-10 pt-6 border-t border-gray-50 flex flex-col sm:flex-row items-center justify-between gap-6">
                <div class="text-center sm:text-left">
                  <p class="text-gray-900 font-black text-[10px] uppercase tracking-widest mb-1">¿Deseas este arreglo?</p>
                  <p class="text-gray-400 text-[9px] italic font-serif">Respuesta inmediata por especialistas</p>
                </div>
                
                <a :href="whatsappURL" target="_blank" rel="noopener noreferrer" class="group relative w-full sm:w-auto overflow-hidden">
                  <!-- Efecto de Brillo/Shimmer persistente -->
                  <div class="absolute inset-x-0 top-0 h-full w-full bg-gradient-to-r from-transparent via-white/30 to-transparent -translate-x-full animate-shimmer"></div>
                  
                  <div class="flex items-center justify-center gap-4 bg-gradient-to-br from-[#4D0A46] to-[#831378] text-white px-10 py-5 rounded-2xl font-black text-[10px] tracking-[0.25em] transition-all duration-500 hover:scale-[1.02] hover:shadow-[0_25px_60px_-15px_rgba(77,10,70,0.5)] active:scale-95 group/btn overflow-hidden border border-white/10 uppercase">
                    <!-- Reflejo de Seda (Silk Shimmer) -->
                    <div class="absolute inset-0 bg-gradient-to-r from-transparent via-white/10 to-transparent -translate-x-full group-hover/btn:animate-silk-shimmer"></div>
                    
                    <div class="relative flex items-center gap-4">
                      <!-- Bloque WhatsApp -->
                      <div class="flex items-center gap-2.5">
                         <div class="relative flex items-center justify-center">
                            <MessageCircle class="w-5 h-5 text-white/90" />
                            <div class="absolute -top-1 -right-1 w-2 h-2 bg-green-400 rounded-full animate-pulse shadow-[0_0_8px_rgba(74,222,128,0.8)] border border-[#4D0A46]"></div>
                         </div>
                         <span class="text-[8px] font-bold opacity-60 tracking-normal">WHATSAPP</span>
                      </div>

                      <!-- Separador Senior -->
                      <div class="h-4 w-[1px] bg-white/20"></div>

                      <!-- Bloque Acción -->
                      <div class="flex items-center gap-2">
                        <span class="uppercase"> ENVIAR CONSULTA </span>
                        <ArrowRight class="w-4 h-4 transition-transform duration-500 group-hover/btn:translate-x-1.5" />
                      </div>
                    </div>
                  </div>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@400;700;900&family=Playfair+Display:ital@1&display=swap');

.font-outfit { font-family: 'Outfit', sans-serif; }
.font-serif { font-family: 'Playfair Display', serif; }

/* Animación de Pulso Suave */
@keyframes pulse-subtle {
  0%, 100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(131, 19, 120, 0); }
  50% { transform: scale(1.02); box-shadow: 0 0 20px 5px rgba(131, 19, 120, 0.1); }
}
.animate-pulse-subtle { animation: pulse-subtle 3s infinite ease-in-out; }

/* Animación de Shimmer (Brillo pasando) */
@keyframes shimmer {
  100% { transform: translateX(100%); }
}
/* Animación de Reflejo de Seda (Premium) */
@keyframes silk-shimmer {
  0% { transform: translateX(-100%); opacity: 0; }
  20% { opacity: 1; }
  80% { opacity: 1; }
  100% { transform: translateX(100%); opacity: 0; }
}
.group-hover\/btn\:animate-silk-shimmer { animation: silk-shimmer 1.8s cubic-bezier(0.4, 0, 0.2, 1) infinite; }

.modal-fade-enter-active, .modal-fade-leave-active {
  transition: all 0.4s ease-out;
}
.modal-fade-enter-from, .modal-fade-leave-to {
  opacity: 0;
}
.modal-fade-enter-from div.relative, .modal-fade-leave-to div.relative {
  transform: translateY(20px);
  opacity: 0;
}

.custom-scrollbar::-webkit-scrollbar { width: 4px; }
.custom-scrollbar::-webkit-scrollbar-track { background: transparent; }
.custom-scrollbar::-webkit-scrollbar-thumb { background: #f0f0f0; border-radius: 2px; }
.custom-scrollbar::-webkit-scrollbar-thumb:hover { background: #831378; }
</style>
