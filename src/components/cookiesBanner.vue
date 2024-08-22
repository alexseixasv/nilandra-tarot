<template>
    <div v-if="!isBannerDismissed" class="fixed bottom-0 inset-x-0 bg-purple-900 text-white py-3 px-6 flex items-center justify-between z-50">
      <div class="flex items-center">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-5 m-2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 6H5.25A2.25 2.25 0 0 0 3 8.25v10.5A2.25 2.25 0 0 0 5.25 21h10.5A2.25 2.25 0 0 0 18 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25" />
        </svg>
        <p class="text-xs">
          Usamos cookies próprios e de terceiros em nossos sites para melhorar sua experiência, analisar nosso tráfego e para segurança e marketing. Selecione "Aceitar Tudo" para permitir o uso. Leia nossa <a href="#" class="underline hover:text-purple-300">Política de Cookies</a>.
        </p>
      </div>
      <button @click="acceptCookies" type="button" class="bg-white text-purple-800 px-4 py-2 rounded-full hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-purple-500 text-base">
        Aceitar
      </button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isBannerDismissed: false
      }
    },
    mounted() {
      // Verifica se o banner foi rejeitado
      this.isBannerDismissed = localStorage.getItem('cookieConsent') === 'true';
    },
    methods: {
      acceptCookies() {
        // Define o banner como rejeitado e armazena no localStorage por 10 dias
        localStorage.setItem('cookieConsent', 'true');
        this.isBannerDismissed = true;
      }
    }
  }
  </script>
  