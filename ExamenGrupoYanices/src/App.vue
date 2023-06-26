<script setup>
  import {ref} from 'vue';
  let likes = ref(28);
  let disLikes = ref(3);
  let pass = 0;
  let like_p = document.querySelector('.like_p');
  let disLike_p = document.querySelector('.disLike_p');

  const acumularLike = () => { 
    if (pass >= 0) {
      likes.value += 1;
      disLikes.value -= 1;
    }
    if(pass == 0) {
      disLikes.value += 1;
    }
    if(pass == -1) {
      likes.value -= 1;
      pass = 0;
      like_p.classList.remove('activeLike');
      return;
    }
    pass = -1;
    like_p.classList.add('activeLike');
    disLike_p.classList.remove('activeDislike');
  }

  const acumularDislike = () => {
    if (pass <= 0) {
      disLikes.value += 1;
      likes.value -= 1;
    }
    if(pass == 0) {
      likes.value += 1;
    }
    if(pass == 1) {
      disLikes.value -= 1;
      pass = 0;
      disLike_p.classList.remove('activeDislike');
      return;
    }
    pass = 1;
    like_p.classList.remove('activeLike');
    disLike_p.classList.add('activeDislike');
  }

</script>

<template>

  <div class="flex flex-col bg-white p-5 w-[500px] rounded-2xl gap-2">

    <div class="flex justify-between items-center">
      <p>Historias</p>
      <p class="px-4 p-2 bg-blue-300 rounded-lg text-white cursor-pointer">Todas</p>
    </div>

    <div class="Historias flex justify-between p-3">

      <span>
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg"
          class="w-24 h-24 mb-2 rounded-lg border-4 border-blue-400"
        />
        <p>Floppa</p>
      </span>

      <span>
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg"
          class="w-24 h-24 mb-2 rounded-lg border-4 border-blue-400"
        />
        <p>Floppa</p>
      </span>

      <span>
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg"
          class="w-24 h-24 mb-2 rounded-lg border-4 border-blue-400"
        />
        <p>Floppa</p>
      </span>

      <span>
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg"
          class="w-24 h-24 mb-2 rounded-lg border-4 border-blue-400"
        />
        <p>Floppa</p>
      </span>

    </div>

    <div class="Publi flex flex-col gap-3">

      <div class="flex items-center gap-5 relative">

        <img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg" class="w-20 h-20 rounded-full">

        <span class="">
          <h2 class="font-bold text-lg">Amongus</h2>
          <p class="opacity-70">Suspiro de alivio</p> 
        </span>

        <i class="absolute right-0 text-red-500 font-bold text-lg">Reportar</i>

      </div>

      <img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg" class="w-full rounded-3xl">

      <div class="flex gap-3 text-2xl items-center">

        <i class="fa-regular fa-heart text-red-700 hover:scale-125 duration-150" @click="acumularLike"></i>
        <p class="like_p text-base opacity-70" ref="like_p">{{likes}}</p>
        <i class="fa-regular fa-thumbs-down text-amber-400 hover:scale-125 duration-150" @click="acumularDislike" ref="fillThumbs"></i>
        <p class="disLike_p text-base opacity-70" ref="disLike_p">{{ disLikes }}</p>

      </div>

    </div>

    <div class="bg-[#ededed] text-[40px] rounded-lg flex justify-around items-center py-4 mt-3 relative">

      <i class="fa-regular fa-heart text-red-700 hover:scale-125 duration-150 z-10"></i>
      <i class="fa-regular fa-heart text-red-700 hover:scale-125 duration-150 z-10"></i>
      <i class="fa-regular fa-heart text-red-700 hover:scale-125 duration-150 z-10"></i>
      <span class="absolute w-[55px] h-[55px] bg-white rounded-2xl"></span>

    </div>

  </div>

</template>

<style scoped>

  .activeLike {
    color: red;
    font-weight: bold;
  }
  .activeDislike {
    color: orangered;
    font-weight: bold;
  }

</style>
