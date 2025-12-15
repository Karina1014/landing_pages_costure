<template>
  <footer id="contact" class="bg-[#831378] text-white pt-16 pb-6">
    <div class="max-w-7xl mx-auto px-4">

      <div class="max-w-5xl mx-auto grid grid-cols-12 gap-8 items-start">

        <!-- Huella -->
        <div class="col-span-12 md:col-span-3 flex justify-start">
          <img src="../../assets/logo/logoSinFondoBlanco.png" alt="Huella" class="h-40" />
        </div>

        <!-- Contáctanos -->
        <div class="col-span-12 md:col-span-4 text-sm">
          <h3 class="text-xl font-bold mb-4">Contáctanos</h3>

          <div class="space-y-2">
            <div>
              <p class="font-semibold">Carolina</p>
              <p>Galo Plaza Lasso N15-392, Quito (Pichincha)</p>
              <p>0959749898</p>
              <p>admi.medvet@gmail.com</p>
            </div>
          </div>
        </div>

        <!-- Horarios -->
        <div class="col-span-12 md:col-span-5 text-sm">
          <h3 class="text-xl font-bold mb-4">Horarios de Atención</h3>

          <div class="space-y-2">
            <div>
              <p class="font-semibold">CAROLINA</p>
              <p>Lunes a Jueves: 8:00 am - 8:30 pm</p>
              <p>Viernes: 8:00 am - 6:00 pm</p>
              <p>Sábado: No tenemos atención</p>
              <p>Domingo: 8:00 am - 8:00 pm</p>
            </div>

          </div>
        </div>

      </div>


      <!-- Redes sociales -->
      <div class="mt-8 flex justify-center gap-6">
        <SocialIcons link="https://www.facebook.com/veterimedvet/" name="ri-facebook-fill" />
        <SocialIcons link="https://www.instagram.com/medvet58/" name="ri-instagram-fill" />
        <SocialIcons link="https://www.tiktok.com/@medvet_ec" name="ri-tiktok-fill" />
      </div>

      <!-- Derechos -->
      <div class="mt-10 border-t border-white/30 pt-4 text-center text-sm">
        &copy; {{ currentYear }} CosturaRous | Todos los derechos reservados
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
import SocialIcons from './SocialIcons.vue'
// import Dog from './Dog.vue'

const currentYear = ref(new Date().getFullYear())
</script>

<style scoped>
@keyframes moveRight {
  0% {
    left: 0;
  }
  100% {
    left: calc(100% - 150px);
  }
}

.scroll-container-simple {
  width: 100%;
  height: 160px;
  overflow: hidden; /* Oculta contenido que se salga */
  position: relative;
}

.lottie-wrapper-simple {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 150px;
  height: 150px;
  animation: moveRight 8s linear infinite;
}

</style>