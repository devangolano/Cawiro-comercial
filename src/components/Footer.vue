<template>
  <footer
    class="bottom-0 left-0 z-20 w-full p-4 bg-[#1f2937] border-t border-gray-200 shadow md:flex md:items-center md:justify-around md:p-6 dark:bg-gray-800 dark:border-gray-600">
    <ul
      class="font-medium flex  justify-around px-4 md:px-0 mt-2  md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 ">
      <li>
        <a href="#" class="block py-2 px-3 text-white md:hover:text-blue-700 hover:text-blue-700  md:p-0 "
          aria-current="page"><router-link to="/">Inicio</router-link></a>
      </li>
      <li>
        <a href="#"
          class="block py-2 px-3 text-white  md:hover:bg-transparent md:border-0 hover:text-blue-700 md:hover:text-blue-700 md:p-0 md:dark:hover:text-blue-500 md:dark:hover:bg-transparent"><router-link
            to="/sobre">Sobre</router-link></a>
      </li>
      <li>
        <a href="#"
          class="block py-2 px-3 text-white  md:hover:bg-transparent md:border-0 hover:text-blue-700 md:hover:text-blue-700 md:p-0 md:dark:hover:text-blue-500 md:dark:hover:bg-transparent"><router-link
            to="/Servicos">Serviços</router-link></a>
      </li>
    </ul>
    <span class="text-sm flex flex-col justify-center items-center md:block text-white sm:text-center dark:text-white">
      <a href="#" class="hover:underline">© 2024 Cawiro (SU)™</a> Todos os direitos Reservados.
    </span>
  </footer>

</template>
<script setup>

</script>
