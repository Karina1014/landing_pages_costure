<template>
  <div class="gallery-container" :class="{ 'is-loaded': isLoaded }">
    <!-- Versión Escritorio: Columnas Verticales con Rotación -->
    <div class="gallery-wrapper hidden lg:flex">
      
      <!-- Columna 1 -->
      <div class="marquee-column col-slow">
        <div class="marquee-content">
          <div v-for="(img, i) in [...col1, ...col1]" :key="'c1-'+i" class="image-card">
            <img :src="img" alt="Costura Art" />
          </div>
        </div>
      </div>

      <!-- Columna 2 -->
      <div class="marquee-column col-fast offset-column">
        <div class="marquee-content">
          <div v-for="(img, i) in [...col2, ...col2]" :key="'c2-'+i" class="image-card">
            <img :src="img" alt="Costura Art" />
          </div>
        </div>
      </div>
    </div>

    <!-- Versión Móvil: Carrusel Automático Compacto -->
    <div class="mobile-gallery lg:hidden">
      <div class="mobile-marquee">
        <div class="mobile-scroll-content animate-marquee-horizontal">
          <div v-for="(img, i) in [...imgs, ...imgs]" :key="'mob-'+i" class="mobile-image-card">
            <img :src="img" alt="Atelier Detail" />
          </div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isLoaded = ref(false)

const imgs = [
  new URL('@/assets/home/costura5.gif', import.meta.url).href,
  new URL('@/assets/home/tailoring.png', import.meta.url).href,
  new URL('@/assets/home/colagador.jpeg', import.meta.url).href,
  new URL('@/assets/home/Negocio1 (2).jpeg', import.meta.url).href,
  new URL('@/assets/home/Negocio1 (3).jpeg', import.meta.url).href,
  new URL('@/assets/home/arreglov1.jpeg', import.meta.url).href,
  new URL('@/assets/home/Negocio1 (1).jpeg', import.meta.url).href,
]

const col1 = [imgs[0], imgs[1], imgs[2], imgs[3]]
const col2 = [imgs[4], imgs[5], imgs[6], imgs[0]]

onMounted(() => {
  setTimeout(() => {
    isLoaded.value = true
  }, 100)
})
</script>

<style scoped>
.gallery-container {
  position: relative;
  width: 100%;
  height: auto;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  opacity: 0;
  transition: opacity 1s ease;
}

.gallery-container.is-loaded {
  opacity: 1;
}

/* ESTILOS MÓVIL (COMPACTO) */
.mobile-gallery {
  width: 100vw;
  margin-left: -1.5rem;
  margin-right: -1.5rem;
  overflow: hidden;
  padding: 0.5rem 0; /* Padding mínimo */
}

.mobile-marquee {
  display: flex;
  overflow: hidden;
}

.mobile-scroll-content {
  display: flex;
  gap: 0.75rem; /* Gap más apretado */
  width: max-content;
}

.animate-marquee-horizontal {
  animation: marquee-h 25s linear infinite;
}

@keyframes marquee-h {
  0% { transform: translateX(0); }
  100% { transform: translateX(calc(-50% - 0.375rem)); }
}

.mobile-image-card {
  width: 125px; /* Más pequeño para minimalismo */
  height: 125px;
  border-radius: 1rem;
  overflow: hidden;
  box-shadow: 0 4px 15px -3px rgba(0, 0, 0, 0.08);
  flex-shrink: 0;
}

.mobile-image-card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* ESTILOS ESCRITORIO */
@media (min-width: 1024px) {
  .gallery-container {
    height: 700px;
    overflow: visible;
  }

  .gallery-wrapper {
    display: flex;
    gap: 2.5rem;
    transform: rotate(-3deg); 
    transform-origin: center;
    scale: 0.9;
  }

  .marquee-column {
    display: flex;
    flex-direction: column;
    width: 250px;
    overflow: hidden;
  }

  .col-slow { --duration: 50s; }
  .col-fast { --duration: 40s; }
  .offset-column { margin-top: -100px; }

  .marquee-content {
    display: flex;
    flex-direction: column;
    gap: 2.2rem;
    animation: scroll-vertical var(--duration) linear infinite;
  }

  @keyframes scroll-vertical {
    from { transform: translate3d(0, 0, 0); }
    to { transform: translate3d(0, -50%, 0); }
  }

  .image-card {
    width: 100%;
    aspect-ratio: 4/5.5; 
    border-radius: 1.5rem; 
    overflow: hidden;
    box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.08);
  }

  .image-card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
</style>