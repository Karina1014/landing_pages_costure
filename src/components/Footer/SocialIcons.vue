<template>
  <a 
    :href="link" 
    target="_blank" 
    rel="noopener noreferrer"
    class="social-link group"
  >
    <component :is="iconComponent" class="w-5 h-5 transition-transform duration-500 group-hover:scale-110" />
    <div class="absolute inset-0 bg-white/10 rounded-full scale-0 group-hover:scale-100 transition-transform duration-500"></div>
  </a>
</template>

<script setup>
import { computed } from 'vue'
import { Facebook, Instagram, Twitter, Music2 } from 'lucide-vue-next'

const props = defineProps({
  link: { type: String, required: true },
  name: { type: String, required: true } // 'facebook', 'instagram', 'tiktok', etc.
})

const iconComponent = computed(() => {
  switch (props.name.toLowerCase()) {
    case 'facebook': return Facebook
    case 'instagram': return Instagram
    case 'tiktok': return Music2 // Lucide no tiene TikTok oficial, usamos Music2 que es el estándar para TikTok
    default: return Twitter
  }
})
</script>

<style scoped>
.social-link {
  position: relative;
  width: 44px;
  height: 44px;
  display: flex;
  items: center;
  justify-content: center;
  color: white;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 9999px;
  transition: all 0.5s ease;
  overflow: hidden;
}

.social-link:hover {
  border-color: white;
  background: white;
  color: #831378;
}
</style>