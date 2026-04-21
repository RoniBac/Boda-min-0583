<template>
  <section class="hero"  v-if="imagen">
    
    <!-- Imagen -->
    <img :src="imagen" alt="Hero" class="hero-img">

    <!-- Contenido encima -->
    <div class="hero-overlay">
      <p class="fecha">— {{ fecha }} —</p>
      <h1 class="nombres">

        <span class="nombre novia">
          {{ novia }}
        </span>

        <span class="and">&</span>

        <span class="nombre novio">
          {{ novio }}
        </span>

      </h1>
      <img class="icono" :src="icono" alt="Icono">
    </div>

  </section>
</template>

<script setup>
defineProps({
  imagen: String,
  fecha: String,
  novia: String,
  novio: String,
  icono: String
})
</script>