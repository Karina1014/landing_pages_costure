<template>
  <Navbar />
  <!-- Contenedor principal: columna en móvil (TokinPromo primero), fila en escritorio -->
  <div class="min-h-screen flex flex-col lg:flex-row">
    <!-- Sección TokinPromo (izquierda en escritorio, primero en móvil) -->
    <div class="w-full lg:w-1/2 bg-white p-6 flex items-center justify-center">
      <HomeLeft />
    </div>
    <!-- Sección VerticalMarquee (derecha en escritorio, segundo en móvil) -->
    <div class="w-full lg:w-1/2 bg-white p-4 flex items-center justify-center">
      <HomeRigth />
    </div>
  </div>
  <About />
  <Services />
  <Whatsapp />
  <Testimonio />
  <Group />
  <VisitSection />
  <Footer />
</template>

<script setup>
import Navbar from './components/home/Navbar.vue'
import HomeLeft from './components/home/HomeLeft.vue'
import HomeRigth from './components/home/HomeRigth.vue'
import About from './components/About/About.vue'
import Services from './components/Services/Services.vue'
import Whatsapp from './components/Whatsapp.vue';
import Testimonio from './components/About/Testimonio.vue';
import Group from './components/About/GroupWorket.vue';
import VisitSection from './components/About/VisitSection.vue';
import Footer from './components/Footer/Footer.vue';
</script>
