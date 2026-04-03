<template>
  <div id="inicio" class="pt-20 lg:pt-28 pb-12 lg:pb-20 min-h-[70vh] flex flex-col lg:flex-row bg-white w-full items-center px-6 sm:px-12 lg:px-24 overflow-hidden relative">
    <!-- Elementos Decorativos -->
    <div class="absolute top-0 left-0 w-full h-full bg-[#FAF9FC] -z-10"></div>
    
    <!-- Sección HomeLeft (Texto) -->
    <div class="w-full lg:w-[45%] flex items-center justify-center lg:justify-start">
      <HomeLeft />
    </div>
    
    <!-- Sección HomeRigth (Galería) -->
    <div class="w-full lg:w-[55%] flex items-center justify-center lg:justify-end mt-12 lg:mt-0">
      <HomeRigth />
    </div>
  </div>
</template>

<script setup>
import HomeLeft from './HomeLeft.vue'
import HomeRigth from './HomeRigth.vue'
</script>

<style scoped>
/* Estilos específicos del Hero si fuesen necesarios */
</style>
