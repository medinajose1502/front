<template>
  <div id="app">
    <Cabecera/>
    <Crud/>
    <Tabla/>
    <Grafico/>
  </div>
</template>

<script>
import Cabecera from './components/Cabecera.vue'
import Crud from './components/Crud.vue'
import Grafico from './components/Grafico.vue'
import Tabla from './components/Tabla.vue'

export default {
  name: 'App',
  components: {
    Cabecera,
    Crud,
    Grafico,
    Tabla,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
