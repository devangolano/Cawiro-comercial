<template>
  <div>
    <Navbar :logo="logo_src" :alt="app_name" :selecao="selecao" />
    <Banner />
    <BurgerForm @novo-hamburger="adicionarHamburger" />
    <div>
      <router-view></router-view>
    </div>
    <Footer />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'; // Adicionando importação de ref
import 'flowbite';
import Banner from './components/Banner'
import Navbar from './components/Navbar'
import BurgerForm from './components/BurgerForm'
import Footer from './components/Footer'
import { initFlowbite } from 'flowbite'

onMounted(() => {
  initFlowbite();
})

const logo_src = ref("/cwr1.png");
const app_name = ref("logotipo da empresa");

const selecao = ref([
  { id: 1, nome: "Item 1", descricao: "Descrição do Item 1", preco: 10 },
]);

const adicionarHamburger = (novoHamburger) => {
  if (selecao.value.length > 0) {
    selecao.value[0].nome = novoHamburger.nome;
    selecao.value[0].descricao = novoHamburger.descricao;
    selecao.value[0].preco = novoHamburger.preco;
  } else {
    selecao.value.push({
      id: 1,
      nome: novoHamburger.nome,
      descricao: novoHamburger.descricao,
      preco: novoHamburger.preco
    });
  }
};
</script>

<style>
* {
  font-family: Helvetica;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>