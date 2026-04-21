<script setup>
import { ref } from 'vue';
import { 
  Scissors, 
  Sparkles, 
  Wrench, 
  Shirt, 
  Star, 
  Home, 
  ChevronDown, 
  ExternalLink 
} from 'lucide-vue-next';

// Components
import ServicesModal from './ServicesModal.vue';

// Assets
import img1 from "@/assets/home/Costura1.png";
import img2 from "@/assets/home/costura2.png";
import img3 from "@/assets/home/costura3.png";
import img4 from "@/assets/home/costura4.png";
import img5 from "@/assets/home/Negocio1 (1).jpeg";
import img6 from "@/assets/home/Negocio1 (2).jpeg";

const isModalOpen = ref(false);
const selectedCategoryData = ref(null);

const pillars = [
  {
    id: 'core',
    title: "SERVICIOS QUE OFRECE",
    icon: Scissors,
    color: "bg-[#831378]",
    bg: img1,
    snippet: "Bastas • Cuellos • Cinturas",
    description: "Servicios fundamentales de sastrería con precisión milimétrica para un ajuste impecable.",
    services: [
      "Virada de cuellos",
      "Alzada de bastas",
      "Metida de bastas",
      "Ajuste de cintura (Pantalones o Faldas)",
      "Dobladillos (Pantalones, Faldas y Vestidos)",
      "Ajuste de largo de mangas (Chompas, Vestidos)",
      "Estrechar o ensanchar prendas"
    ]
  },
  {
    id: 'modificaciones',
    title: "MODIFICACIONES DE PRENDAS",
    icon: Sparkles,
    color: "bg-[#4294BD]",
    bg: img2,
    snippet: "Estilo • Escotes • Personalización",
    description: "Transformamos la esencia de tu ropa para adaptarla a tu visión personal.",
    services: [
      "Cambio de estilo (Escotes, Mangas, Cortes)",
      "Personalización total de ropa",
      "Combinar dos prendas diferentes",
      "Transformar vestidos/faldas a pantalones",
      "Diseño de cuellos nuevos (Gamuza, Felpa)",
      "Acoplar shorts a minifaldas",
      "Aumentar o quitar mangas",
      "Aumento de capuchas"
    ]
  },
  {
    id: 'reparaciones',
    title: "REPARACIONES",
    icon: Wrench,
    color: "bg-[#A78BFA]",
    bg: img3,
    snippet: "Cierres • Botones • Costuras",
    description: "Restauración técnica para devolver la funcionalidad y estética a tus prendas.",
    services: [
      "Cambio de cierres",
      "Cambio de botones",
      "Reparación de costuras descosidas",
      "Arreglo de roturas o huecos",
      "Refuerzo de prendas desgastadas",
      "Pegada de parches técnicos",
      "Cambio de elásticos"
    ]
  },
  {
    id: 'especificas',
    title: "PRENDAS ESPECÍFICAS",
    icon: Shirt,
    color: "bg-[#10B981]",
    bg: img4,
    snippet: "Jeans • Uniformes • Formal",
    description: "Tratamiento especializado según el tipo de tejido y uso de la prenda.",
    services: [
      "Ajuste de Jeans (Entubado, Tiro, Largo)",
      "Arreglo de uniformes (Escolares o Laborales)",
      "Modificación de prendas deportivas",
      "Ajuste de ropa formal (Sacos, Pantalones de vestir)"
    ]
  },
  {
    id: 'especiales',
    title: "SERVICIOS ESPECIALES",
    icon: Star,
    color: "bg-[#F59E0B]",
    bg: img5,
    snippet: "Trajes • Disfraces • Delicados",
    description: "Atención meticulosa para piezas de alta complejidad o materiales sensibles.",
    services: [
      "Modificación de trajes de baño",
      "Modificación de disfraces",
      "Arreglo de ropa delicada (Encaje, Seda, etc.)",
      "Ajustes personalizados al cuerpo",
      "Copia de prendas (Replicar piezas favoritas)",
      "Reparación de zapatos de ballet",
      "Arreglo de fajas quirúrgicas",
      "Arreglo de brasiers"
    ]
  },
  {
    id: 'hogar',
    title: "HOGAR & CONFECCIÓN",
    icon: Home,
    color: "bg-[#EC4899]",
    bg: img6,
    snippet: "Cojines • Cortinas • Carpas",
    description: "Soluciones textiles integrales para tu espacio y accesorios complementarios.",
    services: [
      "Confección de cojines y cobertores",
      "Confección de manteles de mesa",
      "Confecciones sencillas (Fundas, Cortinas)",
      "Arreglo de carpas y guantes",
      "Arreglo de corbatas",
      "Aumento de bolsillos técnicos",
      "Aumento de puños (Calentadores, Licras)"
    ]
  }
];

const openModal = (category) => {
  selectedCategoryData.value = category;
  isModalOpen.value = true;
};

const handleInteraction = (pillar, event) => {
  // Mobile: Click para abrir
  // Desktop: Hover para abrir
  if (window.innerWidth > 1024) {
    if (event.type === 'mouseenter') openModal(pillar);
  } else {
    if (event.type === 'click') openModal(pillar);
  }
};
</script>

<template>
  <section id="servicios" class="w-full bg-[#FAF9FC] pt-6 lg:pt-10 pb-8 font-outfit">
    <!-- Header Editorial -->
    <div class="max-w-7xl mx-auto px-6 mb-6 lg:mb-10 text-center">
      <span class="text-[10px] font-black uppercase tracking-[0.4em] text-[#831378] mb-2 lg:mb-3 inline-block opacity-60">
        Atelier de Alta Costura
      </span>
      <h2 class="text-3xl sm:text-4xl lg:text-6xl font-black text-gray-900 leading-tight tracking-tighter mb-4">
        Servicios que <span class="text-[#831378]">Elevan</span> tu Imagen
      </h2>
      
      <div class="flex items-center justify-center gap-3 animate-pulse-subtle">
        <div class="h-[1px] w-6 bg-[#831378]/20"></div>
        <p class="text-[#831378] font-bold text-[10px] uppercase tracking-widest bg-[#831378]/5 px-5 py-2 rounded-full border border-[#831378]/10">
          Explora nuestras especialidades
        </p>
        <div class="h-[1px] w-6 bg-[#831378]/20"></div>
      </div>
    </div>

    <!-- GRID DE 6 CUADROS (Compactos & Centrados) -->
    <div class="max-w-6xl mx-auto px-4 lg:px-6">
      <div class="flex flex-wrap justify-center gap-4 lg:gap-5">
        
        <div v-for="pillar in pillars" :key="pillar.id"
          class="group relative w-full sm:w-[calc(50%-1rem)] lg:w-[calc(25%-1.25rem)] aspect-[16/10] lg:aspect-[1.1/1] rounded-[1.5rem] lg:rounded-[2rem] overflow-hidden cursor-pointer transition-all duration-500 hover:shadow-2xl hover:-translate-y-1"
          @mouseenter="handleInteraction(pillar, $event)"
          @click="handleInteraction(pillar, $event)"
        >
          <!-- Background Image -->
          <img :src="pillar.bg" :alt="pillar.title" class="absolute inset-0 w-full h-full object-cover grayscale-[30%] group-hover:grayscale-0 transition-all duration-1000 group-hover:scale-110" />
          
          <!-- Dynamic Overlay -->
          <div :class="pillar.color" class="absolute inset-0 opacity-75 mix-blend-multiply transition-opacity group-hover:opacity-60"></div>
          <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/10 to-transparent"></div>

          <!-- Content -->
          <div class="absolute inset-0 p-5 lg:p-6 flex flex-col justify-end items-center text-center">
            <div class="mb-2 transform transition-all duration-500 group-hover:scale-110">
              <component :is="pillar.icon" class="w-6 h-6 lg:w-8 lg:h-8 text-white/90" />
            </div>
            <h3 class="text-base lg:text-lg font-black text-white leading-none uppercase tracking-tighter mb-2">
              {{ pillar.title }}
            </h3>
            <p class="text-white/60 text-[7px] lg:text-[9px] font-bold uppercase tracking-[0.2em] mb-3">
              {{ pillar.snippet }}
            </p>
            
            <div class="px-4 py-1.5 bg-white/10 backdrop-blur-md border border-white/20 rounded-full text-white text-[7px] lg:text-[8px] font-bold uppercase tracking-widest flex items-center gap-2 transition-all hover:bg-white hover:text-black">
              Explorar servicios <ChevronDown class="w-2.5 h-2.5" />
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- MODAL EDITORIAL -->
    <ServicesModal 
      :is-open="isModalOpen" 
      :category="selectedCategoryData" 
      @close="isModalOpen = false"
    />

    <!-- CTA Final -->
    <div class="mt-12 lg:mt-16 text-center px-6">
      <div class="inline-flex flex-col items-center gap-4">
        <p class="text-gray-400 font-bold uppercase text-[9px] tracking-[0.4em]">¿Tienes una prenda única?</p>
        <a href="https://wa.me/593987561663?text=%C2%A1Hola%20Entre%20hilos%20%26%20Agujas!%20Tengo%20una%20consulta%20sobre%20un%20arreglo.%20%C2%BFPodr%C3%ADan%20asesorarme%3F%20%E2%9C%A8" class="px-10 py-4 bg-gray-900 text-white rounded-[1.5rem] font-black text-base transition-all hover:scale-105 shadow-xl">
          Consultar por WhatsApp
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes pulse-subtle {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.8; transform: scale(0.98); }
}
.animate-pulse-subtle { animation: pulse-subtle 3s infinite ease-in-out; }

.backdrop-blur-md { backdrop-filter: blur(8px); }
</style>