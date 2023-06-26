<script setup>

    const props = defineProps({
        Num: {
            type: Number,
            default: 0
        },
        Indice: {
            type: Number,
            default: 0
        }
    })

    function factorial() {
        let factorial = 1;
        for (let i = 0; i < props.Num; i++) {
            factorial *= props.Num - i
        }
        return(factorial)
    }

    const borrarTarjeta = (indice) => { 
        emit('borrarFactorial', indice)
    }

    const emit = defineEmits(['borrarFactorial'])

</script>

<template>

    <div class="bg-slate-400 p-3 flex justify-center items-center flex-1 rounded-lg min-w-[120px] duration-150 hover:scale-105 relative">
        {{ factorial()}}
        <span @click="borrarTarjeta(props.Indice)" class="absolute w-2 h-2 bg-red-600 bottom-0 right-0 m-2 rounded-full cursor-pointer"></span>
    </div>

</template>

<style scoped></style>
