<template>
  <footer id="contact" class="bg-[#831378] text-white pt-16 pb-8">
    <div class="max-w-7xl mx-auto px-6 lg:px-12">

      <div class="grid grid-cols-1 md:grid-cols-12 gap-16 items-start">

        <!-- LOGO & BRAND (Editorial Focus) -->
        <div class="md:col-span-12 lg:col-span-4 flex flex-col items-center lg:items-start space-y-8">
          <div class="relative group">
            <img 
              src="/img/LogoEntreHilos1.webp" 
              alt="Entre Hilos & Agujas Logo" 
              class="h-40 w-auto object-contain transition-transform duration-700 group-hover:scale-105" 
            />
          </div>
          <div class="space-y-2 text-center lg:text-left">
            <p class="text-[11px] font-semi uppercase tracking-[0.5em] text-white-200">
              Entre Hilos & Agujas
            </p>
            <p class="text-[10px] font-medium text-white-400 uppercase tracking-widest italic font-serif">
              Arreglos de Alta Costura & Sastrería Premium
            </p>
          </div>
        </div>

        <!-- CONTACTO (Minimalist) -->
        <div class="md:col-span-6 lg:col-span-4 flex flex-col items-center lg:items-start text-center lg:text-left">
          <h3 class="text-[10px] font-black uppercase tracking-[0.4em] mb-8 text-white-300">Ubicación & Contacto</h3>
          <div class="space-y-6 text-sm">
            <div class="space-y-2">
              <p class="text-white-900 font-black text-xs uppercase tracking-widest">Matriz Carolina</p>
              <p class="text-white-500 font-medium leading-relaxed">
                Galo Plaza Lasso N15-392<br/>
                Sector La Carolina, Quito - Ecuador
              </p>
            </div>
            <div class="space-y-1 pt-2">
              <p class="text-[#831378] font-black text-sm tracking-tighter hover:tracking-widest transition-all duration-500 underline underline-offset-4 decoration-1">
                +593 98 756 1663
              </p>
              <p class="text-white-400 text-[10px] font-bold lowercase tracking-wider">info@entrehilosyagujas.com</p>
            </div>
          </div>
        </div>

        <!-- HORARIOS (Senior Layout) -->
        <div class="md:col-span-6 lg:col-span-4 flex flex-col items-center lg:items-start text-center lg:text-left">
          <h3 class="text-[10px] font-black uppercase tracking-[0.4em] mb-8 text-white-300">Experiencia Atelier</h3>
          <div class="w-full max-w-[280px] space-y-4 text-[11px] font-bold uppercase tracking-widest">
             <div class="flex justify-between items-center border-b border-white-100 pb-2">
                <span class="text-white-400">Lun - Jue</span>
                <span class="text-white-900">08:00 - 20:30</span>
             </div>
             <div class="flex justify-between items-center border-b border-white-100 pb-2">
                <span class="text-white-400">Viernes</span>
                <span class="text-white-900">08:00 - 18:00</span>
             </div>
             <div class="flex justify-between items-center border-b border-white-100 pb-2">
                <span class="text-white-800 italic font-serif opacity-40">Sábado</span>
                <span class="text-white-300">Cerrado</span>
             </div>
             <div class="flex justify-between items-center">
                <span class="text-white-400">Domingo</span>
                <span class="text-white-900">08:00 - 20:00</span>
             </div>
          </div>
        </div>

      </div>

      <!-- SECCIÓN SOCIAL & LEGAL -->
      <div class="mt-20 pt-10 border-t border-white-100 flex flex-col lg:flex-row justify-between items-center gap-10">
        
        <!-- Redes sociales (Atelier Style) -->
        <div class="flex items-center gap-6">
          <SocialIcons link="https://facebook.com/entrehilosyagujas" name="facebook" />
          <SocialIcons link="https://instagram.com/entrehilosyagujas" name="instagram" />
          <SocialIcons link="https://tiktok.com/@entrehilosyagujas" name="tiktok" />
        </div>

        <!-- Derechos (Clean) -->
        <div class="text-center lg:text-right space-y-3">
          <p class="text-[9px] font-black uppercase tracking-[0.3em] text-white-900">
            &copy; {{ currentYear }} Entre hilos & Agujas 
          </p>
         
        </div>

      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
import SocialIcons from './SocialIcons.vue'

const currentYear = ref(new Date().getFullYear())
</script>

<style scoped>
.italic-style {
  font-family: serif;
  font-style: italic;
}

footer {
  position: relative;
  z-index: 20;
}

.social-link {
  position: relative;
  width: 46px;
  height: 46px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #111827;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 9999px;
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.social-link:hover {
  border-color: #831378;
  background: #831378;
  color: white;
  transform: translateY(-4px);
  shadow: 0 10px 25px -5px rgba(131, 19, 120, 0.3);
}
</style>
