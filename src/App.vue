<template>
  <!-- CONTENEDOR MAESTRO: Orquestador Único & Minimalista -->
  <main class="w-full min-h-screen bg-white overflow-x-hidden selection:bg-[#831378]/10 selection:text-[#831378]">
    
    <!-- Navegación Superior -->
    <Navbar />

    <!-- Estructura de Secciones (Master Flow) -->
    <div class="page-content animate-fade-in">
      <Hero />
      <About />
      <Services />
      <Testimonio />
      <Group />
      <VisitSection />
    </div>

    <!-- Pie de Página & Herramientas -->
    <Whatsapp />
    <Footer />
  </main>
</template>

<script setup>
import Navbar from './components/home/Navbar.vue'
import Hero from './components/home/Hero.vue'
import About from './components/About/About.vue'
import Services from './components/Services/Services.vue'
import Whatsapp from './components/Whatsapp.vue';
import Testimonio from './components/About/Testimonio.vue';
// import Group from './components/About/GroupWorket.vue';
import VisitSection from './components/About/VisitSection.vue';
import Footer from './components/Footer/Footer.vue';
</script>

<style>
/* Estilos Globales de Orquestación */
.animate-fade-in {
  animation: fadeIn 1.2s cubic-bezier(0.23, 1, 0.32, 1) forwards;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Suavizado de Scroll Global */
html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  padding: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
