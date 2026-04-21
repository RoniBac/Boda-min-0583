<template>
    
    <section class="reveal" >
        <img :src="imagen" alt="Hero" class="hero-img">
    </section> 
</template>

<script setup>
defineProps({
  imagen: String,
})
</script>