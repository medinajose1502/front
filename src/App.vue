<template>
  <div id="app">
    <Cabecera></Cabecera>
    <b-container>

      <b-row>
        <b-col>
          </b-col>
            <b-col>
              <Crud v-on:registrado="agregarAInventario"></Crud>
            </b-col>
          <b-col>
        </b-col>
      </b-row>

      <Tabla productos="productos"></Tabla>
      <Grafico></Grafico>
    </b-container>
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
  },

  data: function() {
   return {
      productos: []
   }
  },

  methods: {
    agregarAInventario(productoAgregado)
    {
      this.productos.push(productoAgregado)
    }
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
