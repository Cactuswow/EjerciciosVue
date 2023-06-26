<script setup>
  import { ref } from 'vue';
  import Hijo from '@/components/HijoComponent.vue'
  let fact = ref();
  let numbers = ref([]);
  
  const mostrarFactorial  = () => {
    numbers.value.push(fact.value);
  }

  const borrarFactorial = (indice) => {
    numbers.value.splice(indice, 1)
  }

</script>

<template>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  
  <div class="bg-green-700 flex flex-col gap-4 py-5 justify-center items-center">
    <input type="number" class="text-black text-center p-2 rounded-2xl outline-none" v-model="fact" />
    <button class="bg-white text-black p-3 rounded" @click="mostrarFactorial">Mostrar Factorial</button>
  </div>

  <div class="max-w-[600px] mx-auto mt-6 rounded-lg flex flex-wrap gap-3">

    <Hijo v-for="(number, indice) in numbers" :key="indice" :Num = number :Indice = indice @borrarFactorial = borrarFactorial></Hijo>

  </div>

</template>

<style scoped></style>
