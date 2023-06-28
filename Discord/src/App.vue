<script setup>
import { ref } from 'vue';
import Chat from './components/chatComponent.vue';

  let contactos = ref([
    {
      name : 'Marcos Pérez',
      actividad : 'hace 10 minutos',
      mensajes : [
        {
          msj : 'Hola, espero estés muy bien',
          fecha : '25/06/2023',
          hora : '10: 55 am'
        },
        {
          msj : 'Necesito un favor',
          fecha : '25/06/2023',
          hora : '10: 56 am'
        },
        {
          msj : 'Comete una empanada',
          fecha : '25/06/2023',
          hora : '10: 57 am'
        }
      ]
    },
    {
      name : 'Juana Contreras',
      actividad : 'Ayer',
      mensajes : [
        {
          msj : 'Sin V-if xd',
          fecha : '25/06/2023',
          hora : '10: 55 am'
        },
        {
          msj : 'Curioso',
          fecha : '25/06/2023',
          hora : '10: 57 am'
        },
        {
          msj : 'Verdad que sí',
          fecha : '25/06/2023',
          hora : '11: 56 am'
        }
      ]
    },
    {
      name : 'Marcos Pérez',
      actividad : 'hace una hora',
      mensajes : [
        {
          msj : 'Ni idea que más poner',
          fecha : '25/06/2023',
          hora : '10: 55 am'
        },
        {
          msj : 'Curiosa la hora',
          fecha : '25/06/2023',
          hora : '10: 64 am'
        },
        {
          msj : 'Kactuswow',
          fecha : 'Sus momento',
          hora : 'Kactuswow am'
        }
      ]
    }
  ])
  let contactoMostrar = ref(contactos.value[0]);

  const MostrarChat = (contacto) => {
    contactoMostrar.value = contacto;
  }
</script>

<template>
  <div class="bg-gray-500 flex rounded-md overflow-hidden text-white">

    <div class="aside p-3 bg-gray-700 text-blue-300">

      <img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg" class="w-20 h-20 rounded-lg mb-2" >
      <a class="block text-center">Perfil</a>

    </div>

    <div class="p-4 w-[400px] bg-gray-600">

      <h2 class="text-2xl mb-4">Tendencias</h2>
      <ul class="flex flex-col gap-3 mb-5">
        <li>#Titanic</li>
        <li>#Titanic</li>
        <li>#Titanic</li>
        <li>#Titanic</li>
        <li>#Titanic</li>
        <li>#Titanic</li>
      </ul>

      <h2 class="text-2xl mb-4">Mensajes directos</h2>
      <div class="flex flex-col gap-4">

        <div class="flex gap-3 items-center bg-gray-500 py-2 px-4 rounded-lg" v-for="(contacto, indice) in contactos" :key="indice" @click="MostrarChat(contacto)">

          <img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg" class="w-24 h-24 rounded-full">

          <div class="">
            <h3 class="text-xl">{{ contacto.name }}</h3>
            <p>{{ contacto.actividad}}</p>
          </div>

        </div>

      </div>

    </div>

    <div class="w-[500px] p-4">

      <Chat  :contacto = "contactoMostrar"></Chat>

    </div>

    <div class="publicidad p-4 bg-gray-600">

      <h2 class="text-2xl mb-7">Publicidad</h2>

      <img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg" class="w-48 h-48 rounded-2xl mb-5">
      <img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg" class="w-48 h-48 rounded-2xl">


    </div>

  </div>
</template>

<style scoped>

</style>
