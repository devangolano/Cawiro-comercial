<template>
  <div>
    <Navbar :logo="logo_src" :alt="app_name" />
    <div>
      <router-view></router-view>
    </div>
    <Footer />
  </div>
</template>

<script setup>
import 'flowbite';
import Navbar from './components/Navbar'
import Footer from './components/Footer'
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

onMounted(() => {
  initFlowbite();
})

const logo_src = "/cwr1.png";
const app_name = "logotipo da empresa";
</script>

<style>
* {
  font-family: Helvetica;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
