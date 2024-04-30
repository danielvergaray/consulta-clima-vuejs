<script setup>
import Formulario from './components/Formulario.vue';
import useClima from './composables/useClima';
import Clima from './components/Clima.vue';
import Spinner from './components/Spinner.vue'
import Alerta from './components/Alerta.vue';

const {obtenerClima, clima, mostrarClima, cargando, error} = useClima()


</script>

<template>
    <h1 class="titulo">Buscador de Clima</h1>

    <div class="contenedor buscador-clima">
      <Formulario @obtener-clima="obtenerClima"/>
      <Spinner v-if="cargando"/>
      <Alerta v-if="error">{{ error }}</Alerta>
      <Clima v-if="mostrarClima" :clima="clima"/>
    </div> 
    
  
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
