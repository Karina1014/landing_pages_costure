<template>
  <nav class="fixed top-0 left-0 w-full z-[999] bg-[#D6D2E0] px-6 py-2 flex justify-center shadow-[0_4px_20px_rgba(0,0,0,0.08)] backdrop-blur-sm bg-opacity-95">
    <div class="w-full max-w-7xl flex items-center justify-between relative">

      <!-- Logo & Branding -->
      <a href="/" class="flex items-center gap-4 group">
        <div class="relative">
          <img src="/img/LogoEntreHilos1.webp" alt="Logo" class="h-18 w-auto transition-transform duration-500 group-hover:scale-110" />
          <div class="absolute -inset-1 bg-[#831378] opacity-0 group-hover:opacity-10 rounded-full blur transition-opacity"></div>
        </div>
        <div class="flex flex-col">
          <span class="text-xl md:text-2xl font-black text-[#831378] tracking-tighter leading-none">Costura</span>
          <span class="text-[10px] md:text-xs font-bold text-gray-700 tracking-[0.2em] uppercase mt-1">Entre Hilos & Agujas</span>
        </div>
      </a>

      <!-- Menú Escritorio (Centrado Absoluto) -->
      <ul class="hidden lg:flex items-center gap-10 absolute left-1/2 -translate-x-1/2">
        <li>
          <a href="/" class="text-gray-900 font-bold hover:text-[#831378] transition-all relative after:content-[''] after:absolute after:bottom-[-4px] after:left-0 after:w-0 after:h-[2px] after:bg-[#831378] after:transition-all hover:after:w-full">Inicio</a>
        </li>
        <li>
          <a href="#sobreNosotros" class="text-gray-900 font-bold hover:text-[#831378] transition-all relative after:content-[''] after:absolute after:bottom-[-4px] after:left-0 after:w-0 after:h-[2px] after:bg-[#831378] after:transition-all hover:after:w-full">Quiénes Somos</a>
        </li>
        <li>
          <a href="#servicios" class="text-gray-900 font-bold hover:text-[#831378] transition-all relative after:content-[''] after:absolute after:bottom-[-4px] after:left-0 after:w-0 after:h-[2px] after:bg-[#831378] after:transition-all hover:after:w-full">Servicios</a>
        </li>
        <li>
          <a href="#Plan" class="text-gray-900 font-bold hover:text-[#831378] transition-all relative after:content-[''] after:absolute after:bottom-[-4px] after:left-0 after:w-0 after:h-[2px] after:bg-[#831378] after:transition-all hover:after:w-full">Testimonios</a>
        </li>
      </ul>

      <!-- Botón Localización (Derecha) -->
      <div class="flex items-center gap-4">
        <a href="#sucursales" class="hidden md:flex items-center gap-2 bg-[#831378] text-white font-bold px-6 py-2.5 rounded-xl shadow-lg shadow-[#831378]/20 hover:bg-[#6c1063] hover:-translate-y-0.5 transition-all active:scale-95">
          <MapPinned class="w-5 h-5" />
          <span>Localización</span>
        </a>

        <!-- Menú Hamburguesa -->
        <button @click="isOpen = !isOpen" class="lg:hidden p-2 text-[#4294BD] hover:bg-white/20 rounded-lg transition-colors focus:outline-none">
          <svg class="w-8 h-8" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
            <path v-if="!isOpen" stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
            <path v-else stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
    </div>

    <!-- Menú Móvil -->
    <transition name="mobile-menu">
      <div v-if="isOpen" class="lg:hidden absolute top-full left-0 w-full bg-[#D6D2E0] border-t border-black/5 shadow-2xl px-6 py-8">
        <ul class="flex flex-col gap-6 text-center">
          <li><a @click="isOpen = false" href="#inicio" class="text-xl font-black text-gray-900 hover:text-[#831378]">Inicio</a></li>
          <li><a @click="isOpen = false" href="#sobreNosotros" class="text-xl font-black text-gray-900 hover:text-[#831378]">Quiénes Somos</a></li>
          <li><a @click="isOpen = false" href="#servicios" class="text-xl font-black text-gray-900 hover:text-[#831378]">Servicios</a></li>
          <li><a @click="isOpen = false" href="#Plan" class="text-xl font-black text-gray-900 hover:text-[#831378]">Testimonios</a></li>
          <li class="pt-4">
            <a @click="isOpen = false" href="#sucursales" class="inline-flex items-center gap-2 bg-[#831378] text-white font-bold px-10 py-4 rounded-2xl shadow-xl">
              <MapPinned /> Localización
            </a>
          </li>
        </ul>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { MapPinned, ChevronUp } from 'lucide-vue-next'

const isOpen = ref(false)
const showScrollTop = ref(false)

const handleScroll = () => {
  showScrollTop.value = window.scrollY > 300
}

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
/* Transición del menú móvil (Senior) */
.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
}

.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

/* Scroll Top Button (Estilo Refinado) */
.scroll-top-btn {
  position: fixed;
  bottom: 30px;
  right: 30px;
  background: #831378;
  color: white;
  border: none;
  border-radius: 12px;
  padding: 10px;
  cursor: pointer;
  box-shadow: 0 10px 20px rgba(131, 19, 120, 0.3);
  transition: all 0.3s ease;
  opacity: 0;
  transform: translateY(20px);
  z-index: 9999;
}

.scroll-top-btn.visible {
  opacity: 1;
  transform: translateY(0);
}

.scroll-top-btn:hover {
  background-color: #6c1063;
  transform: scale(1.1);
}
</style>
