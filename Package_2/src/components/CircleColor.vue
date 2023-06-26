<script setup>
import { ref } from 'vue';


    let props = defineProps({
        color : {
            type : String,
            default : '#000'
        },
        indice: {
            type: Number,
            default: 0
        }
    })

    let color = 'background :' + props.color;
    let inputColorHijo = ref();
    let emit = defineEmits(['borrarTarjeta'], ['duplicarTarjeta'], ['cambiarColor']);

    const borrarTarjeta = () => {
        emit('borrarTarjeta', props.indice);
    }
    const duplicarTarjeta = () => {
        emit('duplicarTarjeta', props.color);
    }
    const cambiarColor = () => {
        emit('cambiarColor', props.indice, inputColorHijo.value);
    }


</script>

<template>
    <div class="relative flex justify-center items-center flex-1 min-w-[120px] py-7 rounded-3xl" v-bind:style="color">

        <span class="w-20 h-20 rounded-full overflow-hidden border-2">
            <input type="Color" class="w-full h-full scale-150" v-model="inputColorHijo" @input="cambiarColor">
        </span>

        <span class="absolute w-10 h-10 border-2 bg-red-700 rounded-full -top-4 -right-4 cursor-pointer" @click="borrarTarjeta"></span>

        <span class="absolute bottom-0 right-0 m-4 w-4 h-4 rounded-full bg-white border-2" @click="duplicarTarjeta"></span>

  </div>
</template>

<style scoped></style>
