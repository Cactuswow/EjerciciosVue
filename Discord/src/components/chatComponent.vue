<script setup>

    let mostrarU = defineProps({
        contacto : {
            
        }
    })

</script>

<template>

    <h1 class="font-bold text-3xl mb-4">{{ mostrarU.contacto.name}}</h1>

    <div class="flex flex-col gap-4">

        <div class=" px-4 py-3 bg-slate-700 rounded-lg" v-for="(mensaje, indice) in mostrarU.contacto.mensajes" :key="indice">
        
            <p>{{ mensaje.msj }}</p>
            <p class="text-end">{{ mensaje.fecha }}  {{ mensaje.hora }}</p>
            
        </div>

    </div>

</template>