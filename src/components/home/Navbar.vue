<template>
  <nav class="fixed top-0 left-0 w-full z-[999] bg-[#D6D2E0] px-4 py-3 flex justify-center shadow-md">
    <div class="w-full max-w-[960px] flex items-center justify-between relative">

      <!-- Logo -->
      <!-- <a href="/" class="flex items-center">
        <img src="/img/Logo-Medvet.png" alt="Logo" class="h-[60px] w-auto" />
      </a> -->

      <!-- Menú Escritorio -->
        <ul class="hidden lg:flex gap-8 font-medium text-black text-base">
          <a href="/" class="hover:text-[#4E3D7A] transition-colors">Inicio</a>
        <li><a href="#sobreNosotros" class="hover:text-[#4E3D7A] transition-colors">Sobre Nosotros</a></li>
        <li><a href="#servicios" class="hover:text-[#4E3D7A] transition-colors">Servicios</a></li>
        <li><a href="#Plan" class="hover:text-[#4E3D7A] transition-colors">VetPlan</a></li>

      </ul>

     <!-- Botón GPS Escritorio -->
         <a href="#sucursales" class="hidden lg:flex items-center gap-2 bg-[#4E3D7A] text-white font-bold px-4 py-2 rounded-full hover:bg-blue-500 transition-colors">
          <MapPinned /> Localización
        </a>
      <!-- Botón hamburguesa (móvil) -->
      <button @click="isOpen = !isOpen" class="lg:hidden text-[#4E3D7A] focus:outline-none">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path
            :class="{ 'hidden': isOpen }"
            stroke-linecap="round" stroke-linejoin="round"
            d="M4 6h16M4 12h16M4 18h16"
          />
          <path
            v-if="isOpen"
            stroke-linecap="round" stroke-linejoin="round"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>
    </div>

    <!-- Menú móvil -->
    <transition name="fade">
      <div v-if="isOpen" class="lg:hidden absolute top-full left-0 w-full bg-[#EFF1F5] px-4 py-3">
        <ul class="flex flex-col gap-4 text-right font-medium text-black text-base">
          <li><a href="#inicio" class="hover:text-[#0c9AD1] transition-colors">Inicio</a></li>
          <li><a href="#servicios" class="hover:text-[#0c9AD1] transition-colors">Servicios</a></li>
          <li><a href="#contacto" class="hover:text-[#0c9AD1] transition-colors">Sobre Nosotros</a></li>
          <li>
            <button class="flex items-center gap-2 bg-[#12538B] text-white px-4 py-2 rounded-full hover:bg-blue-500 transition-colors ml-auto">
              <MapPinned /> Localización
            </button>
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
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

.scroll-top-btn {
  position: fixed;
  bottom: 135px;
  right: 30px;
  background-color: #0C99D1;
  color: white;
  border: none;
  border-radius: 50%;
  padding: 0.8rem;
  font-size: 0.5rem;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
  transition:
    opacity 0.4s ease,
    transform 0.4s ease;
  opacity: 0;
  transform: scale(0.8);
  pointer-events: none;
  z-index: 9999;
}

.scroll-top-btn.visible {
  opacity: 1;
  transform: scale(1);
  pointer-events: auto;
}

.scroll-top-btn:hover {
  background-color: #3b82f6;
  transform: scale(1.1);
}

.icon {
  width: 24px;
  height: 24px;
}
</style>
