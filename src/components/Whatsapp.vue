<template>
  <div class="fixed bottom-6 left-6 z-[9999] flex flex-col items-start gap-4">
    
    <!-- Burbuja de Saludo (Temporal: 3 Segundos) -->
    <transition name="slide-fade">
      <div 
        v-if="showGreeting" 
        class="bg-white/95 backdrop-blur-xl border border-white/50 shadow-[0_20px_50px_-15px_rgba(0,0,0,0.2)] rounded-3xl p-5 max-w-[240px] relative animate-bounce-subtle"
      >
        <div class="flex items-center gap-3 mb-2">
          <div class="w-2 h-2 rounded-full bg-green-500 animate-pulse"></div>
           <p class="text-[10px] font-black uppercase tracking-[0.2em] text-[#831378]">Taller Costura</p>
        </div>
        <p class="text-sm text-gray-800 font-bold leading-tight">¿Tienes alguna duda con tu ropa? ✨</p>
        <!-- Flecha del Popup -->
        <div class="absolute -bottom-2 left-8 w-4 h-4 bg-white/95 border-r border-b border-white/50 rotate-45"></div>
      </div>
    </transition>

    <!-- Botón Principal (Logo Oficial) -->
    <div
      class="relative group"
      @mouseenter="showPopup = true"
      @mouseleave="showPopup = false"
      @click="toggleMobilePopup"
    >
      <a
        :href="whatsappURL"
        target="_blank"
        rel="noopener noreferrer"
        class="relative block transition-all duration-700 hover:rotate-[360deg] hover:scale-110 active:scale-90"
      >
        <!-- Efecto de Anillo Pulsante (Senior) -->
        <div class="absolute inset-0 bg-green-500 rounded-full animate-ping opacity-20 group-hover:opacity-40"></div>
        
        <div class="w-16 h-16 bg-[#25D366] rounded-full shadow-[0_20px_40px_-5px_rgba(37,211,102,0.4)] flex items-center justify-center border-4 border-white relative z-10 overflow-hidden group-hover:shadow-[0_25px_50px_-12px_rgba(37,211,102,0.6)] transition-all">
          <!-- Logo Oficial SVG -->
          <svg viewBox="0 0 24 24" class="w-9 h-9 fill-white">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
          </svg>
        </div>
      </a>

      <!-- Popup flotante (Manual) -->
      <transition name="fade-up">
        <div
          v-show="showPopup"
          class="absolute bottom-full left-0 mb-6 w-72 bg-white/95 backdrop-blur-xl border border-white shadow-[0_30px_60px_-15px_rgba(0,0,0,0.3)] rounded-[2rem] p-6 transition-all duration-500"
        >
          <div class="flex flex-col gap-5">
            <div class="flex items-center gap-3">
              <div class="relative w-10 h-10 rounded-full overflow-hidden border border-green-500/20">
                <img src="https://images.unsplash.com/photo-1594824476967-48c8b964273f?auto=format&fit=crop&q=80&w=100" class="w-full h-full object-cover" />
                <div class="absolute bottom-0 right-0 w-3 h-3 bg-green-500 border-2 border-white rounded-full"></div>
              </div>
              <div>
                <p class="font-black text-gray-900 text-[10px] uppercase tracking-widest leading-none">Asesoría Directa</p>
                <p class="text-[9px] font-bold text-green-600 mt-1 uppercase tracking-tighter">Atención inmediata</p>
              </div>
            </div>
            <p class="text-gray-600 text-sm font-medium italic-style leading-relaxed">
              "Cuéntanos qué necesitas y te daremos la mejor solución técnica en tiempo récord."
            </p>
            <a
              :href="whatsappURL"
              target="_blank"
              rel="noopener noreferrer"
              class="block bg-gray-900 text-white text-center py-4 rounded-2xl font-black text-[10px] uppercase tracking-[0.2em] hover:bg-[#831378] transition-all duration-300 shadow-xl"
            >
              Iniciar Conversación
            </a>
          </div>
        </div>
      </transition>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const phoneNumber = '593987561663'
const message = '¡Hola Entre hilos & Agujas! Tengo una consulta sobre un arreglo. ¿Podrían ayudarme? ✨'
const whatsappURL = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`

const showPopup = ref(false)
const showGreeting = ref(false)

const toggleMobilePopup = () => {
  showPopup.value = !showPopup.value
}

onMounted(() => {
  // Aparece a los 1.5s
  setTimeout(() => {
    showGreeting.value = true
    
    // Desaparece después de 3s de ser visible (total 4.5s)
    setTimeout(() => {
      showGreeting.value = false
    }, 3000)
    
  }, 1500)
})
</script>

<style scoped>
.italic-style {
  font-family: serif;
  font-style: italic;
}

@keyframes bounce-subtle {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-5px); }
}

.fade-up-enter-active,
.fade-up-leave-active {
  transition: all 0.6s cubic-bezier(0.23, 1, 0.32, 1);
}

.fade-up-enter-from,
.fade-up-leave-to {
  opacity: 0;
  transform: translateY(20px) scale(0.9);
}

.slide-fade-enter-active {
  transition: all 0.6s cubic-bezier(0.23, 1, 0.32, 1);
}
.slide-fade-leave-active {
  transition: all 0.6s cubic-bezier(1, 0, 0, 1);
}

.slide-fade-enter-from {
  transform: translateX(-30px);
  opacity: 0;
}

.slide-fade-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}
</style>
