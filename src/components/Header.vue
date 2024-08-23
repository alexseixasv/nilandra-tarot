<template>
  <header class="absolute inset-x-0 top-0 z-50">
    <!-- Barra de notificação -->
    <div v-if="isNotificationVisible" class="relative isolate hidden lg:flex items-center gap-x-6 overflow-hidden bg-black px-6 py-2.5 sm:px-3.5 sm:before:flex-1">
      <div class="absolute left-[max(-7rem,calc(50%-52rem))] top-1/2 -z-10 -translate-y-1/2 transform-gpu blur-2xl" aria-hidden="true">
        <div class="aspect-[577/310] w-[36.0625rem] bg-gradient-to-r from-[#ff80b5] to-[#9089fc] opacity-30" style="clip-path: polygon(74.8% 41.9%, 97.2% 73.2%, 100% 34.9%, 92.5% 0.4%, 87.5% 0%, 75% 28.6%, 58.5% 54.6%, 50.1% 56.8%, 46.9% 44%, 48.3% 17.4%, 24.7% 53.9%, 0% 27.9%, 11.9% 74.2%, 24.9% 54.1%, 68.6% 100%, 74.8% 41.9%)"></div>
      </div>
      <div class="absolute left-[max(45rem,calc(50%+8rem))] top-1/2 -z-10 -translate-y-1/2 transform-gpu blur-2xl" aria-hidden="true">
        <div class="aspect-[577/310] w-[36.0625rem] bg-gradient-to-r from-[#ff80b5] to-[#9089fc] opacity-30" style="clip-path: polygon(74.8% 41.9%, 97.2% 73.2%, 100% 34.9%, 92.5% 0.4%, 87.5% 0%, 75% 28.6%, 58.5% 54.6%, 50.1% 56.8%, 46.9% 44%, 48.3% 17.4%, 24.7% 53.9%, 0% 27.9%, 11.9% 74.2%, 24.9% 54.1%, 68.6% 100%, 74.8% 41.9%)"></div>
      </div>
      <div class="flex flex-wrap items-center gap-x-4 gap-y-2">
        <p class="text-sm leading-6 text-white">
          <strong class="font-semibold">50% OFF na primeira consulta</strong><svg viewBox="0 0 2 2" class="mx-2 inline h-0.5 w-0.5 fill-current" aria-hidden="true"><circle cx="1" cy="1" r="1" /></svg>Oferta por tempo limitado.
        </p>
        <a href="https://api.whatsapp.com/send?phone=5511937007820&text=Que+bom+que+chegou+até+aquihttps%3A%2F%2Fw.app%2FDHXmJz" target="_blank" class="flex-none rounded-full bg-purple-900 px-3.5 py-1 text-sm font-semibold text-white shadow-sm hover:bg-gray-700 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-gray-900">Garantir oferta <span aria-hidden="true">&rarr;</span></a>
      </div>
      <div class="flex flex-1 justify-end">
        <button type="button" @click="hideNotification" class="-m-3 p-3 focus-visible:outline-offset-[-4px]">
          <span class="sr-only">Dismiss</span>
          <svg class="h-5 w-5 text-white" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
            <path d="M6.28 5.22a.75.75 0 00-1.06 1.06L8.94 10l-3.72 3.72a.75.75 0 101.06 1.06L10 11.06l3.72 3.72a.75.75 0 101.06-1.06L11.06 10l3.72-3.72a.75.75 0 00-1.06-1.06L10 8.94 6.28 5.22z" />
          </svg>
        </button>
      </div>
    </div>

    <!-- Navegação e menu móvel -->
    <nav class="flex items-center justify-between p-6 lg:px-8" aria-label="Global">
      <div class="flex lg:flex-1">
        <a href="#" class="-m-1.5 p-1.5">
          <img class="h-12 w-auto" src="../../src/assets/main-logo.svg" alt="">
        </a>
      </div>
      <div class="flex lg:hidden">
        <button 
          type="button" 
          @click="toggleMenu" 
          class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700">
          <span class="sr-only">Open main menu</span>
          <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
          </svg>
        </button>
      </div>
      <div class="hidden lg:flex lg:gap-x-12">
        <a href="https://bio.nilandratarot.com.br/" target="_blank" class="text-sm font-semibold leading-6 text-gray-900">Banhos</a>
        <a href="https://www.instagram.com/stories/highlights/17968311239636567/" target="_blank" class="text-sm font-semibold leading-6 text-gray-900">Depoimentos</a>
        <a href="https://www.instagram.com/nilandrataro" target="_blank" class="text-sm font-semibold leading-6 text-gray-900">Instagram</a>
        <a href="https://bio.nilandratarot.com.br/" target="_blank" class="text-sm font-semibold leading-6 text-gray-900">Hoodoo</a>
      </div>
      <div class="hidden lg:flex lg:flex-1 lg:justify-end">
        <a href="https://api.whatsapp.com/send?phone=5511937007820&text=Que+bom+que+chegou+at%C3%A9+aquihttps%3A%2F%2Fw.app%2FDHXmJz" target="_blank" class="text-sm font-semibold leading-6 text-gray-900">Agendar consulta <span aria-hidden="true">&rarr;</span></a>
      </div>
    </nav>
    <!-- Mobile menu, show/hide based on menu open state. -->
    <div v-if="isMenuOpen" class="lg:hidden" role="dialog" aria-modal="true">
      <!-- Background backdrop, show/hide based on slide-over state. -->
      <div class="fixed inset-0 z-50"></div>
      <div class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
        <div class="flex items-center justify-between">
          <a href="#" class="-m-1.5 p-1.5">
            <img class="h-8 w-auto" src="../assets/main-logo.svg" alt="">
          </a>
          <button type="button" @click="closeMenu" class="-m-2.5 rounded-md p-2.5 text-gray-700">
            <span class="sr-only">Close menu</span>
            <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
        <div class="mt-6 flow-root">
          <div class="-my-6 divide-y divide-gray-500">
            <div class="space-y-2 py-6">
              <a href="https://bio.nilandratarot.com.br/" target="_blank" class="-mx-3 block rounded-lg py-1.5 px-3 text-base font-semibold leading-6 text-gray-900 hover:bg-gray-100">Banhos</a>
              <a href="https://www.instagram.com/stories/highlights/17968311239636567/" target="_blank" class="-mx-3 block rounded-lg py-1.5 px-3 text-base font-semibold leading-6 text-gray-900 hover:bg-gray-100">Depoimentos</a>
              <a href="https://www.instagram.com/nilandrataro" target="_blank" class="-mx-3 block rounded-lg py-1.5 px-3 text-base font-semibold leading-6 text-gray-900 hover:bg-gray-100">Instagram</a>
              <a href="https://bio.nilandratarot.com.br/" target="_blank" class="-mx-3 block rounded-lg py-1.5 px-3 text-base font-semibold leading-6 text-gray-900 hover:bg-gray-100">Hoodoo</a>
            </div>
            <div class="py-6">
              <a href="https://api.whatsapp.com/send?phone=5511937007820&text=Que+bom+que+chegou+at%C3%A9+aquihttps%3A%2F%2Fw.app%2FDHXmJz" target="_blank" class="-mx-3 block rounded-lg py-1.5 px-3 text-base font-semibold leading-6 text-gray-900 hover:bg-gray-100">Agendar consulta <span aria-hidden="true">&rarr;</span></a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue';

const isNotificationVisible = ref(true);
const isMenuOpen = ref(false);

function hideNotification() {
  isNotificationVisible.value = false;
}

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}

function closeMenu() {
  isMenuOpen.value = false;
}
</script>
