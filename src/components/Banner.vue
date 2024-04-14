<template>
  <div id="indicators-carousel" class="relative w-full" data-carousel="static">
    <!-- Carousel wrapper -->
    <div class="relative h-56 overflow-hidden rounded-lg md:min-h-[650px]">
      <!-- Slides -->
      <div v-for="(slide, index) in slides" :key="index"
        :class="{ 'block': index === currentSlide, 'hidden': index !== currentSlide }"
        class="duration-700 ease-in-out absolute w-full -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2">
        <img :src="slide.image" alt="..." class="block w-full">
      </div>
    </div>
    <!-- Slider indicators -->
    <div class="absolute z-30 flex -translate-x-1/2 space-x-3 rtl:space-x-reverse bottom-5 left-1/2">
      <button v-for="(slide, index) in slides" :key="index" type="button"
        :aria-current="index === currentSlide ? 'true' : 'false'" :aria-label="`Slide ${index + 1}`"
        @click="changeSlide(index)" class="w-3 h-3 rounded-full"></button>
    </div>
    <div class="flex flex-col items-center py-4 shadow-md shadow-yellow-600 justify-center">
      <h1 class="text-3xl lg:text-5xl text-yellow-600 font-extrabold">Cawiro Comercial</h1>
      <p class="text-sm lg:text-lg">Cacuaco - Entrada do Eco-campo</p>
      <p class="text-sm lg:text-lg bg-green-500 px-2 py-1 rounded-lg font-semibold mb-2 text-white">Seg á Seg - 10:00 as
        22:00</p>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const slides = ref([
  { image: '/img/image1.jpg' },
  { image: '/img/image2.jpg' },
  { image: '/img/image3.png' },
  { image: '/img/image4.png' },
]);

const currentSlide = ref(0);
let intervalId;

function nextSlide() {
  currentSlide.value = (currentSlide.value + 1) % slides.value.length;
}

function prevSlide() {
  currentSlide.value = (currentSlide.value - 1 + slides.value.length) % slides.value.length;
}

function changeSlide(index) {
  currentSlide.value = index;
}

function startCarousel() {
  intervalId = setInterval(nextSlide, 4000); // Troca de slide a cada 3 segundos
}

function stopCarousel() {
  clearInterval(intervalId);
}

onMounted(() => {
  startCarousel();
});

// Parar o carrossel quando o componente for destruído
onBeforeUnmount(() => {
  stopCarousel();
});
</script>
