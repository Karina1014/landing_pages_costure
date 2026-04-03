<template>
  <footer id="contact" class="bg-[#831378] text-white pt-16 pb-8">
    <div class="max-w-7xl mx-auto px-6 lg:px-12">

      <div class="grid grid-cols-1 md:grid-cols-12 gap-12 items-start">

        <!-- LOGO & BRAND -->
        <div class="md:col-span-4 flex flex-col items-center md:items-start space-y-6">
          <img 
            src="../../assets/logo/logoSinFondoBlanco.png" 
            alt="CosturaRous Logo" 
            class="h-32 w-auto object-contain brightness-0 invert opacity-90 transition-opacity hover:opacity-100" 
          />
          <p class="text-xs font-black uppercase tracking-[0.4em] opacity-60 text-center md:text-left">
            Entre Hilos & Agujas
          </p>
        </div>

        <!-- CONTACTO -->
        <div class="md:col-span-4 text-center md:text-left">
          <h3 class="text-sm font-black uppercase tracking-widest mb-6 opacity-70">Ubicación & Contacto</h3>
          <div class="space-y-4 text-sm font-medium">
            <div class="space-y-1">
              <p class="text-white font-black text-xs uppercase tracking-tighter">Matriz Carolina</p>
              <p class="opacity-80">Galo Plaza Lasso N15-392</p>
              <p class="opacity-80">Quito, Ecuador</p>
            </div>
            <div class="space-y-1 pt-2">
              <p class="opacity-100 font-bold">0959749898</p>
              <p class="opacity-60 text-[11px] font-bold">admi.entrehilos@gmail.com</p>
            </div>
          </div>
        </div>

        <!-- HORARIOS -->
        <div class="md:col-span-4 text-center md:text-left">
          <h3 class="text-sm font-black uppercase tracking-widest mb-6 opacity-70">Experiencia Atelier</h3>
          <div class="space-y-3 text-xs font-medium">
             <div class="flex flex-col md:flex-row md:justify-between items-center md:items-start gap-1">
                <span class="opacity-60">Lunes a Jueves</span>
                <span class="font-black">8:00 am - 8:30 pm</span>
             </div>
             <div class="flex flex-col md:flex-row md:justify-between items-center md:items-start gap-1">
                <span class="opacity-60">Viernes</span>
                <span class="font-black">8:00 am - 6:00 pm</span>
             </div>
             <div class="flex flex-col md:flex-row md:justify-between items-center md:items-start gap-1">
                <span class="opacity-60 italic-style">Sábado (Cerrado)</span>
             </div>
             <div class="flex flex-col md:flex-row md:justify-between items-center md:items-start gap-1">
                <span class="opacity-60">Domingo</span>
                <span class="font-black">8:00 am - 8:00 pm</span>
             </div>
          </div>
        </div>

      </div>

      <!-- SECCIÓN SOCIAL & LEGAL -->
      <div class="mt-16 pt-10 border-t border-white/10 flex flex-col md:flex-row justify-between items-center gap-8">
        
        <!-- Redes sociales (Refinadas) -->
        <div class="flex items-center gap-4">
          <SocialIcons link="https://www.facebook.com/veterimedvet/" name="facebook" />
          <SocialIcons link="https://www.instagram.com/medvet58/" name="instagram" />
          <SocialIcons link="https://www.tiktok.com/@medvet_ec" name="tiktok" />
        </div>

        <!-- Derechos -->
        <div class="text-center md:text-right space-y-2">
          <p class="text-[10px] font-black uppercase tracking-[0.2em] opacity-40">
            &copy; {{ currentYear }} CosturaRous | Ateliers Boutique
          </p>
          <p class="text-[8px] opacity-20 font-bold uppercase tracking-widest">
            Quito • Carolina • Cumbayá
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
</style>
