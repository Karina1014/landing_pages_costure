<template>
  <div class="fixed bottom-5 left-5 z-[9999]">
    <!-- Botón flotante -->
    <div
      class="relative"
      @mouseenter="showPopup = true"
      @mouseleave="showPopup = false"
    >
      <a
        :href="whatsappURL"
        target="_blank"
        rel="noopener noreferrer"
        class="block animate__animated animate__pulse animate__infinite"
      >
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg"
          alt="WhatsApp Icon"
          class="w-14 h-14 rounded-full shadow-lg"
        />
      </a>

      <!-- Popup flotante -->
      <div
        v-show="showPopup"
        class="absolute bottom-full left-0 mb-3 w-72 bg-white border border-green-500 text-green-600 rounded-xl shadow-xl p-4 transition-opacity duration-300"
      >
        <p class="font-bold text-lg mb-2">¿En qué puedo ayudarte?</p>
        <a
          :href="whatsappURL"
          target="_blank"
          rel="noopener noreferrer"
          class="block bg-green-500 text-white text-center py-2 px-4 rounded-lg hover:bg-green-600 transition-colors"
        >
          Chatear en WhatsApp
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const phoneNumber = '+593123456789'
const message = '¡Hola! Quiero obtener más información.'
const whatsappURL = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`

const showPopup = ref(false)
</script>

<style>
@import 'https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css';
</style>
