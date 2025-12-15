<template>
  <section class="relative w-full h-[95vh] max-h-screen overflow-hidden rounded-lg">
    <!-- Imagen de fondo -->
    <img
      :src="backgroundImage"
      :alt="imageAlt"
      class="w-full h-full object-cover rounded-lg"
      loading="lazy"
    />

    <!-- Overlay semitransparente -->
    <div :class="`absolute inset-0 bg-black/${overlayOpacity} rounded-lg`"></div>

    <!-- Contenedor del contenido -->
    <div class="absolute inset-0 flex items-start justify-start p-8 md:p-16 lg:p-20">
      <div class="max-w-3xl">
        <h1 :class="`${titleSize} font-extrabold text-white drop-shadow-xl leading-tight`">
          {{ title }}
        </h1>
        <p v-if="subtitle" class="text-lg md:text-xl text-white/90 drop-shadow-lg mt-4 max-w-xl">
          {{ subtitle }}
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from 'vue'
import TrabajoEnEquipo from '@/assets/home/TrabajoEnEquipo.png'

const props = defineProps({
  backgroundImage: {
    type: String,
    default: TrabajoEnEquipo,
    required: false
  },
  imageAlt: {
    type: String,
    default: 'Equipo de trabajo colaborando',
    required: false
  },
  title: {
    type: String,
    default: 'Equipo de trabajo',
    required: true
  },
  subtitle: {
    type: String,
    default: '',
    required: false
  },
  overlayOpacity: {
    type: String,
    default: '40',
    required: false
  },
  titleSize: {
    type: String,
    default: 'text-4xl md:text-5xl lg:text-6xl',
    required: false
  }
})
</script>

<style scoped>
section {
  background-size: cover;
  background-position: center;
}

/* Animación opcional al cargar */
@media (prefers-reduced-motion: no-preference) {
  img {
    animation: fadeInImage 0.8s ease-in-out;
  }
}

@keyframes fadeInImage {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>