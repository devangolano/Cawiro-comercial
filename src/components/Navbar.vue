<template>
  <div>
    <nav class="bg-gray-900 border-gray-200 dark:bg-gray-900">
      <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto px-4 py-2">
        <router-link to="/">
          <a href="#" class="flex rounded-full justify-center items-center">
            <img :src="logo" :alt="alt" class="md:h-20 h-16" />
          </a>
        </router-link>
        <div class="gap-4">
          <button @click="openCheckout" type="button"
            class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
            aria-controls="navbar-default" :aria-expanded="checkout.toString()">
            <span class="sr-only">Open main menu</span>
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M8 8L8 7C8 4.79086 9.79086 3 12 3V3C14.2091 3 16 4.79086 16 7L16 8" stroke="#E5E7EB"
                stroke-width="2" stroke-linecap="round" />
              <path d="M15 14V12" stroke="#E5E7EB" stroke-width="2" stroke-linecap="round" />
              <path d="M9 14V12" stroke="#E5E7EB" stroke-width="2" stroke-linecap="round" />
              <path
                d="M4 12C4 10.1144 4 9.17157 4.58579 8.58579C5.17157 8 6.11438 8 8 8H16C17.8856 8 18.8284 8 19.4142 8.58579C20 9.17157 20 10.1144 20 12V13C20 16.7712 20 18.6569 18.8284 19.8284C17.6569 21 15.7712 21 12 21V21C8.22876 21 6.34315 21 5.17157 19.8284C4 18.6569 4 16.7712 4 13V12Z"
                stroke="#E5E7EB" stroke-width="2" />
            </svg>
          </button>
          <button @click="toggleMenu" type="button"
            class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
            aria-controls="navbar-default" :aria-expanded="isMenuOpen.toString()">
            <span class="sr-only">Open main menu</span>
            <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M1 1h15M1 7h15M1 13h15" />
            </svg>
          </button>
        </div>
        <div :class="{ 'block': isMenuOpen, 'hidden': !isMenuOpen }" class="w-full md:block md:w-auto"
          id="navbar-default">
          <ul
            class="font-medium flex flex-col justify-around p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
            <li>
              <a href="#" @click="closeMenu"
                class="block py-2 px-3 text-white hover:text-blue-700 rounded md:bg-transparent md:p-0 dark:text-white md:dark:hover:text-blue-500 focus:text-blue-700 focus:outline-none focus:bg-gray-200 focus:ring ring-blue-300"
                aria-current="page"><router-link to="/">Inicio</router-link></a>
            </li>
            <li>
              <a href="#" @click="closeMenu"
                class="block py-2 px-3 text-gray-900 rounded hover:text-blue-700 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"><router-link
                  to="/sobre">Sobre</router-link></a>
            </li>
            <li>
              <a href="#" @click="closeMenu"
                class="block py-2 px-3 text-gray-900 rounded hover:text-blue-700 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"><router-link
                  to="/Servicos">Serviços</router-link></a>
            </li>
            <li>
              <a href="#" @click="closeMenu"
                class="block py-2 px-3 text-gray-900 rounded hover:text-blue-700 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"><router-link
                  to="/Contactos">Contactos</router-link></a>
            </li>
            <div :class="{ 'block': checkout, 'hidden': !checkout }">
              <li>
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M8 8L8 7C8 4.79086 9.79086 3 12 3V3C14.2091 3 16 4.79086 16 7L16 8" stroke="#E5E7EB"
                    stroke-width="2" stroke-linecap="round" />
                  <path d="M15 14V12" stroke="#E5E7EB" stroke-width="2" stroke-linecap="round" />
                  <path d="M9 14V12" stroke="#E5E7EB" stroke-width="2" stroke-linecap="round" />
                  <path
                    d="M4 12C4 10.1144 4 9.17157 4.58579 8.58579C5.17157 8 6.11438 8 8 8H16C17.8856 8 18.8284 8 19.4142 8.58579C20 9.17157 20 10.1144 20 12V13C20 16.7712 20 18.6569 18.8284 19.8284C17.6569 21 15.7712 21 12 21V21C8.22876 21 6.34315 21 5.17157 19.8284C4 18.6569 4 16.7712 4 13V12Z"
                    stroke="#E5E7EB" stroke-width="2" />
                </svg>
              </li>
            </div>
          </ul>
        </div>
      </div>
    </nav>
    <div :class="{ 'block': checkout, 'hidden': !checkout }"
      class=" bg-black/70 w-full h-full flex fixed top-0 left-0 z-[99] items-center justify-center">
      <div class="bg-white p-5 rounded-md min-w-[90%]  md:min-w-[600px]">
        <h2 class="flex items-center justify-center font-bold text-2xl">Meus Pedidos</h2>
        <div id="cart-items" class="flex justify-between mb-2 flex-col"></div>
        <p class="font-bold ">Total: <span class="cart-total">0.00kz</span></p>
        <p class="font-bold mt-4">Endereço de entrega:</p>
        <input type="text" placeholder="Endereço que vai receber..." id="endereco"
          class="w-full border-2 p-2 rounded my-1">
        <p class="text-red-500 hidden" id="endereco-errado">Digite seu emndereço completo</p>
        <div class="flex items-center justify-between py-3">
          <button @click="openCheckout"
            class="bg-red-500 px-2 py-1 text-white cursor-pointer font-semibold rounded-md">Cancelar</button>
          <button class="bg-green-600 px-2 py-1 text-white cursor-pointer font-semibold rounded-md">Finalizar
            Pedido</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  name: "Navbar",
  props: ["logo", "alt"],
  data() {
    return {
      isMenuOpen: false,
      checkout: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    openCheckout() {
      this.checkout = !this.checkout

    },
    closeMenu() {
      this.isMenuOpen = false;
    }
  },
  computed: {
    isCartVisible() {
      return !this.isMenuOpen; // torna a div isCart visível se o menu não estiver aberto
    }
  }
}
</script>
