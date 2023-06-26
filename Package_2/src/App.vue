<script setup>
  import {ref} from 'vue'
  import CircleColor from './components/CircleColor.vue';

  const colors = ref([]);
  let inputColor = ref();

  const AgregarColor = () => {
    colors.value.push(inputColor.value);
  }
  const borrarTarjeta = (indice) => {
    colors.value.splice(indice, 1);
  }
  const duplicarTarjeta = (color) => {
    colors.value.push(color);
  }
  const cambiarColor  = (indice, color) => {
    colors.value[indice] = color;
  }

</script>

<template>
  <div class="bg-green-700 flex flex-col gap-4 py-5 justify-center items-center">

    <span class="rounded-full overflow-hidden w-20 h-20 border-2">
      <input type="Color" class="w-full h-full scale-150" v-model="inputColor">
    </span>

    <button class="bg-white text-black p-3 rounded" @click="AgregarColor">Mostrar Color</button>

  </div>

  <div class="flex flex-wrap gap-7 p-7 w-[700px] mx-auto mt-6">

    <CircleColor v-for="(Color, indice) in colors" :key="indice" :color = "Color" :indice = "indice" @borrarTarjeta="borrarTarjeta" @duplicarTarjeta = "duplicarTarjeta" @cambiarColor = "cambiarColor"></CircleColor>

  </div>
</template>

<style scoped></style>
