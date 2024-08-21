<template>
    <header class="bg-purple-700 text-white p-4">
      <div class="w-full max-w-7xl mx-auto flex justify-between items-center">
        <h1 class="text-3xl font-bold">Nilandra Tarot</h1>
        
        <!-- Ícone de Hambúrguer para Mobile -->
        <button @click="toggleMenu" class="block md:hidden focus:outline-none">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
        
        <!-- Menu de Navegação para Desktop -->
        <nav class="hidden md:block">
          <ul class="flex flex-col md:flex-row space-y-4 md:space-y-0 md:space-x-6">
            <li><a href="#" class="hover:text-purple-300">Início</a></li>
            <li><a href="#" class="hover:text-purple-300">Sobre</a></li>
            <li><a href="#" class="hover:text-purple-300">Serviços</a></li>
            <li><a href="#" class="hover:text-purple-300">Contato</a></li>
          </ul>
        </nav>
      </div>
  
      <!-- Modal do Menu para Mobile -->
      <div v-if="isMenuOpen" class="fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center">
        <div class="bg-white text-black w-4/5 max-w-sm rounded-lg shadow-lg p-6 relative">
          <!-- Botão de Fechar -->
          <button @click="toggleMenu" class="absolute top-2 right-2 focus:outline-none">
            <svg class="w-6 h-6 text-purple-700" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
          
          <!-- Menu de Navegação -->
          <nav>
            <ul class="flex flex-col space-y-6 text-center">
              <li><a href="#" class="hover:text-purple-700">Início</a></li>
              <li><a href="#" class="hover:text-purple-700">Sobre</a></li>
              <li><a href="#" class="hover:text-purple-700">Serviços</a></li>
              <li><a href="#" class="hover:text-purple-700">Contato</a></li>
            </ul>
          </nav>
        </div>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header',
    data() {
      return {
        isMenuOpen: false, // Controle do menu hambúrguer
      };
    },
    methods: {
      toggleMenu() {
        this.isMenuOpen = !this.isMenuOpen;
      },
    },
  };
  </script>
  