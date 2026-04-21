<template>
  <section class="galeria">

    <h2 class="titulo">Momentos Juntos</h2>
    <img :src="data.decoracion" class="decoracion">

    <!-- CONTENEDOR -->
    <div class="viewer">

      <button class="prev" @click="prevImg">❮</button>

      <div class="frame">
        <img :src="imagenes[index]" class="main-img">
      </div>

      <button class="next" @click="nextImg">❯</button>

    </div>

    <!-- THUMBNAILS -->
    <div class="thumbs">
      <img 
        v-for="(img, i) in imagenes" 
        :key="i"
        :src="img"
        @click="setImg(i)"
      >
    </div>

  </section>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  data: Object
})

const imagenes = [
  props.data.foto1,
  props.data.foto2,
  props.data.foto3,
  props.data.foto4,
  props.data.foto5,
  props.data.foto6,
  props.data.foto7,
  props.data.foto8
]

const index = ref(0)

const setImg = (i) => {
  index.value = i
}

const nextImg = () => {
  index.value = (index.value + 1) % imagenes.length
}

const prevImg = () => {
  index.value = (index.value - 1 + imagenes.length) % imagenes.length
}
</script>